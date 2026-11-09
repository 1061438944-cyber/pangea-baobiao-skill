# Pangea 3 图标库

来源：https://www.figma.com/design/RdbGEZDeeMRcWbKbd7ycZr

本 Skill 附带 461 个已导出的 SVG（`assets/icons/名称.svg`），覆盖 7 个分类；商标分类未导出。单色图标使用 `fill="currentColor"`，跟随文字颜色；`upload-*`、`radar-chart` 等多色图标保留原色。

## 使用规则

- 只用下表中实际存在的名称，不自行拼接后缀（例如不存在的 `-fill` 版本）。
- 按语义选图标：收藏（star）与喜欢（heart）、上传（upload）与导出（export）、删除（delete）与关闭（close）不能混用。
- 同一组控件保持尺寸、线性或填充风格一致。常用尺寸 12 / 14 / 16 / 20 / 24px，跟随组件参数。
- 找不到合适图标时说明缺失，给出 2–3 个最接近的候选；未经同意不自绘、不混用其他图标库。
- 单独使用的图标按钮要有 `aria-label` 或文字提示。
- 在 HTML 中内联：读取 `assets/icons/名称.svg`，加上 `class="i" aria-hidden="true"`，尺寸用 CSS 控制。

## 常用语义映射

| 语义 | 图标 |
| --- | --- |
| 首页 | home |
| 搜索 | search |
| 设置 | settings |
| 更多 | more、more-vertical |
| 刷新 | refresh |
| 下载 / 上传 / 导入 / 导出 | download / upload / import / export |
| 编辑 / 删除 / 复制 | edit / delete / copy |
| 附件 / 链接 | attachment / link |
| 用户 / 用户组 | user / user-group |
| 文件 / 文件夹 | file / folder |
| 成功 | check-circle、check-circle-fill |
| 错误 | close-circle、close-circle-fill |
| 信息 | info-circle、info-circle-fill |
| 警告 | exclamation-circle、exclamation-circle-fill、warning |
| 帮助 | question-circle |
| 加 / 减 | plus / minus |
| 关闭 | close |
| 展开收起 | down / up / right / left、caret-* |
| 菜单折叠 | menu-fold / menu-unfold |
| 全屏 | fullscreen / fullscreen-exit |
| AI | ai-assistant、ai-assistant-fill、search-ai 等 |

## 全部图标（按分类）

### 通用（199）

column-setting、transaction、trademark、select、pull-request、pound、percentage、monitor、key、gold、gateway、euro、dollar、deployment-unit、coffee、cluster、ci、barcode、usb、switcher、shop、rocket、rest、reconciliation、money-collect、medicine-box、hourglass、flag、crown、contacts、carry-out、car、build、red-envelope、folder-open、shopping、border、project、control、calculator、inbox、security-scan、property-safety、insurance、block、number、table、shopping-cart、solution、audit、container、wallet、credit-card、laptop、file-sync、file-protect、file-done、exception、cloud-server、account-book、file-search、apartment、alert、explore、bank、heat-map、english-fill、fund、chinese-fill、box-plot、face-smile-fill、radar-chart、face-meh-fill、line-chart、face-frown-fill、dot-chart、bar-chart、area-chart、bookmark、dash、calendar-clock、computer、layers、relation、palette、snippets、language、diff、archive、form、old-version、issues-close、dice、moon-fill、moon、sun-fill、sun、wifi、branch、loading、location、schedule、unlock、email、user-group、dashboard、compass、command、cloud、camera、calendar、bulb、user-add、trophy、tool、thunderbolt、common、upload-default、subscribed、upload-image、subscribe、upload-zip、subscribe-add、upload-pdf、storage、upload-excel、stamp、upload-word、skin、upload-ppt、drive-file、drag-dot、upload-markdown、upload-txt、drag-dot-vertical、desktop、copyright、woman、video-camera、experiment、ear、empty、var、user、api、tags、js、tag、jira、shake、global、bug、pie-chart、book、general、file、subordinates、file-video、reference、file-image、hierarchy、file-pdf、flow、file-audio、dev-process、mosaic、puzzle、safe、robot、mobile、apps、gift、folder、folder-delete、folder-add、fire、mind-mapping、menu、man、loop、lock、layout、interaction、image、image-close、idcard、robot-add、qrcode、pushpin、public、printer、phone、pen-fill、pen、notification、notification-close、nav、mind-map、focus

### 编辑（92）

bg-colors、h1、h2、h3、h4、h5、h6、h7、find-replace、filter、edit、eraser、bold、ordered-list、unordered-list、font-colors、formula、strikethrough、original-size、brush、align-center、align-left、align-right、highlight、italic、line-height、copy、delete、sort-ascending、sort-descending、oblique-line、paste、quote、redo、scissor、zoom-in、zoom-out、sort、underline、link、circular、attachment、display-inline-block、display-inline、display-flex、display-block、justify-space-between-row、justify-space-between-column、justify-space-around-row、justify-space-around-column、justify-flex-start-row、justify-flex-start-column、justify-flex-end-row、justify-flex-end-column、justify-center-row、justify-center-column、direction-row-reverse、direction-row、direction-column-reverse、direction-column、align-stretch-row、align-stretch-column、align-flex-start-row、align-flex-start-column、align-flex-end-row、align-flex-end-column、align-center-row、align-center-column、align-baseline-row、align-baseline-column、card-view、border-bottom、border-horizontal、border-outer、border-left、border-top、border-inner、vertical-align-middle、border-verticle、border-right、pic-left、pic-right、radius-upleft、radius-upright、radius-bottomleft、radius-bottomright、column-height、column-width、font-size、radius-setting、undo、mult-table

### 方向（44）

double-left、double-up、double-right、double-down、expand、shrink、right、left、down、up、menu-fold、menu-unfold、rotate-left、drag-arrow、left-circle、up-circle、up-circle-fill、down-circle-fill、left-circle-fill、right-circle-fill、right-circle、down-circle、rotate-right、swap、to-bottom、to-left、to-right、to-top、caret-down、caret-left、caret-right、caret-up、arrow-fall、arrow-down、arrow-left、arrow-right、arrow-up、multiple、arrow-multiple、arrow-rise、right-square、up-square、down-square、left-square

### 影音（24）

music、backward、forward、fullscreen-exit、fullscreen、live-broadcast、play-arrow、pause、skip-next、skip-previous、sound、mute、play-circle、pause-circle、record-stop、stop-independent、record、sound-fill、mute-fill、play-circle-fill、pause-circle-fill、skip-next-fill、play-arrow-fill、skip-previous-fill

### 交互（57）

star、heart、thumb-down、thumb-up、at、cloud-download、code-block、code-square、code、customer-service、home、import、list、message-banned、message、message-add、more-vertical、more、poweroff、refresh、reply、scan、search、select-all、settings、share-alt、share-external、share-internal、send、download、export、translate、sync、upload、voice、eye-invisible、eye、save、history、launch、star-fill、heart-fill、thumb-down-fill、thumb-up-fill、keyboard、send-fill、enter、add-child、move、select-area、user-delete、usergroup-add、usergroup-delete、disconnect、cast-screen、cloud-upload、cloud-sync

### 提示（29）

exclamation-circle、info-circle、minus-circle、plus-circle、question-circle、check-circle、clock-circle、close-circle、check-square、stop、minus、plus、question、check、close、exclamation、info、check-circle-fill、close-circle-fill、exclamation-circle-fill、exclamation-polygon-fill、info-circle-fill、minus-circle-fill、plus-circle-fill、question-circle-fill、plus-square、close-square、minus-square、warning

### AI（16）

ai-assistant-fill、ai-assistant、search-ai、edit-ai、book-ai、code-ai、global-ai、folder-ai、image-ai、file-ai、audio-ai、video-ai、question-ai、academic-ai、summary-ai、mcp

