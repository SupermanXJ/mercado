# 美客多 Global Selling 文档要点问答

## 商品有哪些大的模块？
- 发布/刊登（Global Listing，创建 global item 与站点 item）
- 分类（Category Predictor、Category Tree）
- 属性（Attributes）
- 商品标识（Product Identifiers，如 GTIN）
- 变体/多属性（Variations）
- 图片（Pictures）
- 描述（Item Description）
- 价格/定价与自动化（Pricing Reference / Manage Automations）
- 库存（Update Stock / Fulfillment Stock）
- 尺码表（Size Chart）
- 目录相关（Catalog Eligibility / Catalog Listing / Catalog Competition）

## 是否支持多站点？并列举出所有站点。
- 支持多站点：Global Listing 支持同时发布到多个 marketplace（示例明确包含 MLM/MLB/MLC/MCO）。
- 站点列表（/sites 接口文档示例中列出）：
  - MLU, MHN, MPT, MRD, MLA, MLM, MCR, MBO, MPE, MSV, MPY, MNI, MLV, MCU, MEC, MLC, MGT, MCO, MLB, MPA

## 支持哪些货币？
- /sites 接口示例的默认货币：UYU, HNL, EUR, DOP, ARS, MXN, CRC, BOB, PEN, USD, PYG, NIO, VES, CUP, CLP, GTQ, COP, BRL, PAB
- Global Selling 刊登要求：global item 价格币种固定为 USD。

## 是否支持单属性和多属性发布商品？
- 支持。无 variations 即单属性；有 variations 即多属性。
- 变体是否可用取决于分类属性标签 allow_variations；若分类允许变体但没有 required 变体属性，可不创建变体。

## 库存逻辑是什么？
- Global item 的 available_quantity 会同步到所有站点（未单独覆盖时）。
- 变体商品按 variation 的 available_quantity 管理库存。
- 库存更新为 0 会触发 status 变为 paused（out_of_stock 子状态）；库存恢复 > 0 会回到 active。
- Fulfillment 场景下，库存使用 inventory_id 追踪，变体有各自 inventory_id。

## 平台分类逻辑是什么？
- 分类按站点区分：通过 /sites/{site_id}/categories 获取站点分类树。
- 发布前用 Category Predictor 预测分类与所需属性。
- category_id 为必填字段，只接受平台预置的分类 ID。

## 商品属性与什么有关？是怎样的关系？
- 属性与分类强相关：/categories/{category_id}/attributes 返回该分类的属性与标签（required/new_required/conditional_required 等）。
- 属性可在 item 层或 variation 层填写，且可修改/删除/新增。

## 多属性商品与什么有关？是怎样的关系？
- 多属性与分类的 allow_variations 及 variation_attribute 标签相关。
- 变体必须在 attribute_combinations 中填写可变体属性；变体自身特性放在 variations[].attributes。

## 哪些模块与分类有关？
- Category Predictor（预测分类）
- Attributes（按分类拉取属性）
- Variations（按分类允许的变体属性）
- Product Identifiers（按分类属性标签要求 GTIN 等）
- Global Listing（category_id 必填）

## 多属性中，子SKU与父SKU是什么关系？
- 文档中仅说明 SKU 使用 SELLER_SKU 属性存储，且可在变体级别填写。
- 未明确给出父/子 SKU 的定义或绑定关系；实际关系体现为同一 global item 下的多个 variation 各自有 SELLER_SKU。

## 是否支持单属性修改为多属性？多属性修改为单属性？
- 支持从单属性变为多属性：可通过 PUT /global/items/{item_id} 添加 variations。
- 多属性删除变体：可在 PUT 中不传某个 variation id 或使用 DELETE /marketplace/items/{item_id}/variations/{variation_id}。
- 文档未明确说明能否从多属性完全转为无 variations 的单属性模式。

## 支持修改哪些属性内容？修改的接口是单个还是多个？列举出修改接口。
- 可修改/新增/删除属性、标题、状态、库存、价格、变体、图片、描述等（部分字段受是否有销量限制）。
- 修改接口是多个，主要包括：
  - PUT https://api.mercadolibre.com/global/items/{ITEM_ID}（更新全局商品、变体、库存、价格、状态等）
  - PUT https://api.mercadolibre.com/global/items/{MARKETPLACE_ITEM_ID}（更新站点商品）
  - PUT https://api.mercadolibre.com/global/items/{ITEM_ID} + body 中 site_id/logistic_type（更新指定站点商品）
  - POST/PUT https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description（新增/替换描述）
  - DELETE https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/variations/{VARIATION_ID}（删除变体）

## 商品有哪些状态？
- Global item 状态：active, paused
- Marketplace item 状态：active, paused, deleted
- 文档还描述了状态含义：Active、Paused、Inactive、Under review

## 商品是否支持彻底删除？
- 文档中仅显示 marketplace item 可能进入 deleted 状态，但未提供删除整条商品的专用接口。

## 是否支持自定义属性?
- 支持：可在 variations 的 attribute_combinations 中使用 API 未定义的自定义属性。

## 通过分类是否可以拉取到属性的填写规则?
- 可以：/categories/{category_id}/attributes 返回属性及 required/new_required/conditional_required 等标签。

## 列举刊登必填项
- sites_to_sell（含 site_id、logistic_type，必要时 price/listing_type_id/title）
- title（英文，且可提供站点本地语言标题）
- description
- currency_id（USD）
- available_quantity（有 variations 时需每个 variation 提供）
- attributes（含必要标签属性、包装尺寸重量等）
- pictures
- category_id
- sale_terms（如 warranty type/time）
- seller_sku（SELLER_SKU 属性）

## 是否存在全球站商品？若存在，全球商品与各站点商品是什么关系？
- 存在：global item 的 site_id 为 CBT。
- global item 创建后会生成 site_items 列表，每个站点有独立 item_id（如 MLB/MLC 等）。
- global item 作为父级，站点 item 作为子级；sites_to_sell 配置决定在哪些站点生成商品。价格/库存在未单独覆盖时由 global item 向站点同步。

## 刊登 listing 和修改 listing 相关接口

### 刊登（创建）
- POST `https://api.mercadolibre.com/global/items`
  - 创建 global item（CBT），可同时配置 `sites_to_sell` 发布到多个站点；支持单属性或 variations 多属性。

### 修改（更新/维护）
- PUT `https://api.mercadolibre.com/global/items/{ITEM_ID}`
  - 更新 global item（CBT）：可改标题、属性、图片、状态、价格、库存、变体等；
  - 也用于更新库存（`available_quantity`）、价格（`price`）、状态（`status`）、变体（`variations`）。

- PUT `https://api.mercadolibre.com/global/items/{MARKETPLACE_ITEM_ID}`
  - 直接更新单个站点 item（例如 MLC/MLB），字段需使用站点本地语言。

- PUT `https://api.mercadolibre.com/global/items/{ITEM_ID}` + body 中 `site_id`/`logistic_type`
  - 使用 CBT ID 更新指定站点 item（与直接对站点 item_id 更新等效）。

- POST `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description`
  - 新增商品描述（纯文本）。

- PUT `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description`
  - 替换/更新商品描述（纯文本）。

- DELETE `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/variations/{VARIATION_ID}`
  - 删除指定变体。

- PUT `https://api.mercadolibre.com/global/items/{ITEM_ID}`（变体更新场景）
  - 变体新增/修改/库存更新需在 `variations` 列表中操作；未提交的 variation id 会被视为删除。

### 查询/详情
- GET `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}`
  - 获取商品详情（global item 或站点 item）。
  - 可通过参数获取特定字段（如 variations）：`?attributes=variations`。
  - 也可使用 `?include_attributes=all` 获取完整属性。

- GET `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description`
  - 获取商品描述（需传 `site_id` 与 `logistic_type`）。

## CBT 与多站点发布问答补充

- 是否可以只刊登到 CBT 而不刊登到其他站点？CBT listing 买家能看见吗？先刊登 CBT 后续再发布多站点可以吗？  
  - 文档要求发布时提供 `sites_to_sell` 来指定要上架的站点，因此按文档理解需要至少选择一个站点发布；CBT 是 global parent，买家是在具体 marketplace 站点看到商品，CBT 不属于买家可见站点。文档未明确“先不选站点、后续再选站点”的流程。

- 已经存在 CBT 的 listing 是否可以发布到其他未发布过的站点中？  
  - 可以。文档明确说明：已有 global listing 可通过 POST `https://api.mercadolibre.com/global/items/{CBT_ITEM_ID}` 并在 `sites_to_sell` 指定新站点来扩展发布。

## 分类与账号关系

- 分类是否与站点有关？  
  - 有关。分类树通过 `GET /sites/{site_id}/categories` 获取，说明分类按站点区分。

- 分类及分类对应的属性是否与用户美客多账号有关？  
  - 文档仅说明与站点/分类相关；账号层面影响可用站点（`/marketplace/users/{user_id}`），未说明分类或属性与账号绑定。

## CBT 分类与站点分类关系补充

- CBT 分类与各站点分类存在什么关系/共性？  
  - 文档未明确映射或对应规则。可确定的共性是：分类决定属性与必填规则（通过 `/categories/{category_id}/attributes`），站点分类通过 `/sites/{site_id}/categories` 获取；CBT/站点均属于平台分类体系，但映射方式未说明。

- CBT 分类 ID 与各站点分类 ID 是否相同？去掉前缀是否相同？  
  - 文档未声明相同。示例里 CBT 分类 ID 以 `CBT` 前缀、站点分类 ID 以站点前缀（如 `MLB/MLM/MLC`）区分，未提供去前缀后的对应规则，因此无法确认。

## 价格/定价自动化逻辑

- 价格/定价的自动化逻辑是什么？  
  - 自动化通过规则动态调价：可选规则 `INT`（站内对比）与 `INT_EXT`（站内+站外对比），系统按规则自动调整价格。  
  - 需要为商品设置 `min_price`/`max_price` 边界；商品需满足可自动化资格。  
  - 若手动修改价格（非自动化），自动化会立即停止以避免价格不一致。  
  - 自动化状态包含 `ACTIVE`/`PAUSED`，可查询、更新或删除自动化规则。

## 库存逻辑补充

- 库存逻辑是什么？如何设置、更改和自动更新？  
  - 全局库存通过 `available_quantity` 管理：无变体商品在 item 层设置，有变体商品在 `variations[].available_quantity` 设置。  
  - 修改库存使用 PUT `/global/items/{ITEM_ID}`：  
    - 无变体：传 `available_quantity`。  
    - 有变体：传 `variations` 列表及各变体 `available_quantity`。  
  - 自动更新：当发生销售时，库存会扣减并反映到 Global Selling（文档说明库存变动会同步反映）。  
  - 库存为 0 会将状态改为 `paused` 且带 `out_of_stock` 子状态；库存恢复 > 0 会回到 `active`。  
  - Fulfillment 场景使用 `inventory_id` 追踪库存，变体有各自的 `inventory_id`。

- CBT 库存与各站点库存有什么关系和联系？  
  - 文档描述：global item 的库存会同步到所有站点；若站点没有单独覆盖，则站点库存与 CBT 保持一致。  
  - 文档未提到“等分分摊”，按描述应为各站点与 CBT 库存数相同（同一个库存数）。  
  - 变体商品在各站点同样使用变体级库存；库存更新在 Global Selling 侧统一反映。

## 目录相关逻辑

- 目录资格：通过 `catalog_listing_eligible` 标签识别可进入目录的商品；也可用搜索 `catalog_listing=true/false` 过滤目录/非目录商品。  
- 目录刊登（Opt-in）：从已有 listing 创建目录商品，需先找到匹配的 `catalog_product_id`，再 POST `/items/catalog_listings`；若原商品有变体，需要按变体分别创建（每个 variation_id 一条）。  
- 目录与变体：有目录的 domain 通常不允许 variations；变体会映射为目录商品的属性。  
- 目录竞争：同一目录商品下的多个 listing 会竞争展示，系统按价格、运费、物流等条件选“winner”；可用 `/items/{ITEM_ID}/price_to_win?siteId=...` 获取竞争状态与建议。  
- 关系数据：目录商品与原 listing 的关系在 `item_relations` 中体现。  
- 目录商品的用意：将同款商品聚合到同一产品页，统一信息并通过竞争机制提升买家体验与转化，卖家通过优化条件获得曝光。  
- 是否类似亚马逊跟卖：在“共享产品页、卖家竞争曝光”层面可类比，但文档未使用“跟卖”概念，具体规则与入口不同。

## 尺码表逻辑

- 适用范围受 domain 限制，需先获取可用 size chart domain，并查看该 domain 的规格表（data sheet）。  
- 尺码表类型：`SPECIFIC`（卖家自定义）与 `BRAND`（品牌尺码表）。  
- 创建尺码表需指定 `domain_id`、`gender`、主尺码字段等，并按规格表定义结构提交行（rows）。  
- 通过 `SIZE_GRID_ID` + `SIZE_GRID_ROW_ID` 关联到商品；变体可关联到不同 row。  
- 尺码表会被校验结构与属性一致性；已关联到商品的尺码表不能直接删除，需先解除关联。

- 如何获取可用 size chart domain？  
  - GET `https://api.mercadolibre.com/catalog/charts/CBT/configurations/active_domains` 返回可用的 `domain_id` 列表（示例为 CBT 站点）。

- 如何查看 domain 的规格表？  
  - GET `https://api.mercadolibre.com/domains/{DOMAIN_ID}/technical_specs` 获取 domain 规格表（用于识别 `grid_template_required` 等标签）。  
  - POST `https://api.mercadolibre.com/domains/{DOMAIN_ID}/technical_specs?section=grids` 获取尺码表结构定义。  
  - POST `https://api.mercadolibre.com/catalog/charts/search` 查询尺码表数据表（需传 domain_id/site_id/seller_id/type/attributes）。

- 尺码表与什么有关？是否与分类有关？  
  - 尺码表与 domain 相关；domain 通常由分类/商品域确定，因此与分类间接相关（文档未给出直接的分类-尺码表映射规则）。

## 描述与图片相关的逻辑和接口

### 描述逻辑
- 描述为纯文本（plain_text），不允许 HTML/特殊字符。
- 新建 global item 后可用 POST 创建描述；已有描述需用 PUT 替换。
- 描述会自动翻译到站点语言；新站点生成后需在 2 天内更新描述。

### 描述接口
- GET `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description?site_id={SITE_ID}&logistic_type={LOGISTIC_TYPE}`
  - 获取指定站点的描述。
- POST `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description`
  - 新增描述（plain_text）。
- PUT `https://api.mercadolibre.com/marketplace/items/{ITEM_ID}/description`
  - 替换/更新描述（plain_text）。

### 图片逻辑
- 图片可能为必填，依赖分类；支持 JPG/JPEG/PNG；尺寸有最小/最大限制。
- 图片可通过两种方式挂载到商品：上传图片获得 `id` 或直接使用 `source` URL。
- 使用 `source` URL 刊登后，图片会被上传到美客多服务器并由美客多域名（如 `http2.mlstatic.com`）托管，不再保留原始 `source` URL。
- 替换/删除图片通过 PUT `global/items` 更新 `pictures` 数组：
  - 替换：仅传新图 ID；
  - 删除：只保留需要保留的 ID；
  - 变体图片在 `variations[].picture_ids` 里维护。

### 图片接口
- POST `https://api.mercadolibre.com/pictures/items/upload`
  - 校验并上传图片（multipart/form-data），返回图片 `id`。
- POST `https://api.mercadolibre.com/items/{ITEM_ID}/pictures`
  - 将已上传图片 `id` 关联到商品。
- PUT `https://api.mercadolibre.com/global/items/{ITEM_ID}`
  - 更新商品图片或变体图片（`pictures` / `variations[].picture_ids`）。
- GET `https://api.mercadolibre.com/pictures/{PICTURE_ID}/errors`
  - 查询图片处理错误。
