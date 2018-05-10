---
title: CStockPropImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
dev_langs:
- C++
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f12cff287b9a9c74b548a08d9a03f73869671fc1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cstockpropimpl-class"></a>CStockPropImpl クラス
このクラスは、ストック プロパティの値をサポートするためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE CStockPropImpl : public IDispatchImpl<InterfaceName, piid,
 plibid,
    wMajor,
 wMinor,
    tihclass>
```   
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コントロールを実装してから派生するクラス`CStockPropImpl`です。  
  
 `InterfaceName`  
 ストック プロパティを公開するデュアル インターフェイスです。  
  
 `piid`  
 IID へのポインター`InterfaceName`です。  
  
 `plibid`  
 定義が含まれるタイプ ライブラリの LIBID へのポインター`InterfaceName`です。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョンです。 既定値は 1 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。  
  
 `tihclass`  
 型情報の管理に使用するクラス`T`です。 既定値は `CComTypeInfoHolder` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|[get_Appearance](#get_appearance)|このメソッドを呼び出して、コントロールで使用してフラット、ペイント スタイルまたは 3D を取得します。|  
|[get_AutoSize](#get_autosize)|このメソッドを呼び出して、コントロールが他のサイズを変更できないかどうかを示すフラグの状態を取得します。|  
|[get_BackColor](#get_backcolor)|コントロールの背景色を取得するには、このメソッドを呼び出します。|  
|[get_BackStyle](#get_backstyle)|透明または不透明のいずれかのコントロールの背景スタイルを取得するには、このメソッドを呼び出します。|  
|[get_BorderColor](#get_bordercolor)|コントロールの境界線の色を取得するには、このメソッドを呼び出します。|  
|[get_BorderStyle](#get_borderstyle)|コントロールの境界線のスタイルを取得するには、このメソッドを呼び出します。|  
|[get_BorderVisible](#get_bordervisible)|かどうかは、コントロールの境界線を表示するかを示すフラグの状態を取得するには、このメソッドを呼び出します。|  
|[get_BorderWidth](#get_borderwidth)|コントロールの境界線の幅をピクセル単位で取得するには、このメソッドを呼び出します。|  
|[get_Caption](#get_caption)|オブジェクトのキャプションで指定したテキストを取得するには、このメソッドを呼び出します。|  
|[get_DrawMode](#get_drawmode)|XOR ペン、色の反転など、コントロールの描画モードを取得するには、このメソッドを呼び出します。|  
|[get_DrawStyle](#get_drawstyle)|実線、破線、点線などのコントロールの描画スタイルを取得するには、このメソッドを呼び出します。|  
|[get_DrawWidth](#get_drawwidth)|このメソッドを呼び出して、描画幅 (ピクセル単位)、コントロールの描画メソッドで使用されるを取得します。|  
|[get_Enabled](#get_enabled)|このメソッドを呼び出して、コントロールが有効になっているかどうかを示すフラグの状態を取得します。|  
|[get_FillColor](#get_fillcolor)|コントロールの塗りつぶしの色を取得するには、このメソッドを呼び出します。|  
|[get_FillStyle](#get_fillstyle)|純色、透明で、またはのクロスハッチなどのコントロールの塗りつぶしのスタイルを取得するには、このメソッドを呼び出します。|  
|[get_Font](#get_font)|このメソッドを呼び出して、コントロールのフォント プロパティへのポインターを取得します。|  
|[get_ForeColor](#get_forecolor)|コントロールの前景色を取得するには、このメソッドを呼び出します。|  
|[get_HWND](#get_hwnd)|コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。|  
|[get_MouseIcon](#get_mouseicon)|(アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを取得するには、このメソッドを呼び出します。|  
|[get_MousePointer](#get_mousepointer)|マウス ポインターの上にマウスがコントロールでは、たとえばときに表示されます、矢印、間、または砂時計の種類を取得するには、このメソッドを呼び出します。|  
|[get_Picture](#get_picture)|このメソッドを呼び出して (アイコン、ビットマップまたはメタファイル) を表示する画像の画像のプロパティへのポインターを取得します。|  
|[get_ReadyState](#get_readystate)|ロードまたはアンロードなどのコントロールの準備完了の状態を取得するには、このメソッドを呼び出します。|  
|[get_TabStop](#get_tabstop)|コントロールがタブ ストップがかどうかかを示すフラグを取得するには、このメソッドを呼び出します。|  
|[get_Text](#get_text)|コントロールに表示されるテキストを取得するには、このメソッドを呼び出します。|  
|[getvalid](#get_valid)|このメソッドを呼び出して、コントロールが有効かどうかを示すフラグの状態を取得します。|  
|[get_Window](#get_window)|コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。 同じ[CStockPropImpl::get_HWND](#get_hwnd)です。|  
|[put_Appearance](#put_appearance)|このメソッドを呼び出して、コントロールで使用してフラット、ペイント スタイルまたは 3D を設定します。|  
|[put_AutoSize](#put_autosize)|コントロールが他のサイズを変更できないかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。|  
|[put_BackColor](#put_backcolor)|コントロールの背景色を設定するには、このメソッドを呼び出します。|  
|[put_BackStyle](#put_backstyle)|コントロールの背景のスタイルを設定するには、このメソッドを呼び出します。|  
|[put_BorderColor](#put_bordercolor)|コントロールの境界線の色を設定するには、このメソッドを呼び出します。|  
|[put_BorderStyle](#put_borderstyle)|コントロールの境界線のスタイルを設定するには、このメソッドを呼び出します。|  
|[put_BorderVisible](#put_bordervisible)|かどうかは、コントロールの境界線を表示するかを示すフラグの値を設定するには、このメソッドを呼び出します。|  
|[put_BorderWidth](#put_borderwidth)|コントロールの境界線の幅を設定するには、このメソッドを呼び出します。|  
|[put_Caption](#put_caption)|コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。|  
|[put_DrawMode](#put_drawmode)|XOR ペン、色の反転など、コントロールの描画モードを設定するには、このメソッドを呼び出します。|  
|[put_DrawStyle](#put_drawstyle)|実線、破線、点線などのコントロールの描画スタイルを設定するには、このメソッドを呼び出します。|  
|[put_DrawWidth](#put_drawwidth)|幅 (ピクセル単位)、コントロールの描画メソッドで使用されるを設定するには、このメソッドを呼び出します。|  
|[put_Enabled](#put_enabled)|コントロールが有効になっているかどうかを示すフラグを設定するには、このメソッドを呼び出します。|  
|[put_FillColor](#put_fillcolor)|コントロールの塗りつぶしの色を設定するには、このメソッドを呼び出します。|  
|[put_FillStyle](#put_fillstyle)|純色、透明で、またはのクロスハッチなどのコントロールの塗りつぶしのスタイルを設定するには、このメソッドを呼び出します。|  
|[put_Font](#put_font)|コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。|  
|[put_ForeColor](#put_forecolor)|コントロールの前景の色を設定するには、このメソッドを呼び出します。|  
|[put_HWND](#put_hwnd)|このメソッドは、E_FAIL を返します。|  
|[put_MouseIcon](#put_mouseicon)|(アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
|[put_MousePointer](#put_mousepointer)|マウス ポインターの上にマウスがコントロールでは、たとえばときに表示されます、矢印、間、または砂時計の種類を設定するには、このメソッドを呼び出します。|  
|[put_Picture](#put_picture)|(アイコン、ビットマップまたはメタファイル) を表示する画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
|[put_ReadyState](#put_readystate)|ロードまたはアンロードなどのコントロールの準備完了の状態を設定するには、このメソッドを呼び出します。|  
|[put_TabStop](#put_tabstop)|コントロールがタブ ストップがかどうかかを示すフラグの値を設定するには、このメソッドを呼び出します。|  
|[put_Text](#put_text)|コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。|  
|[putvalid](#put_valid)|コントロールが有効かどうかを示すフラグを設定するには、このメソッドを呼び出します。|  
|[put_Window](#put_window)|このメソッドを呼び出す[CStockPropImpl::put_HWND](#put_hwnd)E_FAIL が返されます。|  
|[putref_Font](#putref_font)|参照カウントが、コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。|  
|[putref_MouseIcon](#putref_mouseicon)|参照カウントを持つ (アイコン、ビットマップまたはメタファイル)、コントロールの上にマウスが表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
|[putref_Picture](#putref_picture)|参照カウントを持つ (アイコン、ビットマップまたはメタファイル)、表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CStockPropImpl` 提供**put**と**取得**ストックの各プロパティのメソッドです。 これらのメソッドは、各プロパティに関連付けられているデータ メンバーを取得または設定とを通知し、コンテナーと同期して任意のプロパティが変更されたときに必要なコードを提供します。  
  
 Visual C では、そのウィザードを使用するストック プロパティのサポートを提供します。 コントロールへのストック プロパティの追加に関する詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)です。  
  
 旧バージョンと互換性のため、`CStockPropImpl`も公開`get_Window`と`put_Window`メソッドを呼び出すだけを`get_HWND`と`put_HWND`、それぞれします。 既定の実装`put_HWND`返します**E_FAIL**ため`HWND`読み取り専用プロパティである必要があります。  
  
 次のプロパティもが、 **putref**実装します。  
  
-   フォント  
  
-   MouseIcon  
  
-   Picture  
  
 同じ 3 つのストック プロパティがそれぞれ対応するデータ メンバー型にする必要があります`CComPtr`か適切なインターフェイスの参照を提供する他のクラスは、代入演算子を使用してカウントします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="get_appearance"></a>  CStockPropImpl::get_Appearance  
 このメソッドを呼び出して、コントロールで使用してフラット、ペイント スタイルまたは 3D を取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnAppearance*  
 コントロールの描画スタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_autosize"></a>  CStockPropImpl::get_AutoSize  
 このメソッドを呼び出して、コントロールが他のサイズを変更できないかどうかを示すフラグの状態を取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAutoSize*  
 フラグの状態を受け取る変数。 TRUE は、コントロールが他のサイズを変更できないことを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_backcolor"></a>  CStockPropImpl::get_BackColor  
 コントロールの背景色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrBackColor*  
 コントロールの背景色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_backstyle"></a>  CStockPropImpl::get_BackStyle  
 透明または不透明のいずれかのコントロールの背景スタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnBackStyle*  
 コントロールの背景のスタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_bordercolor"></a>  CStockPropImpl::get_BorderColor  
 コントロールの境界線の色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrBorderColor*  
 コントロールの境界線の色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_borderstyle"></a>  CStockPropImpl::get_BorderStyle  
 コントロールの境界線のスタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnBorderStyle*  
 コントロールの境界線のスタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_bordervisible"></a>  CStockPropImpl::get_BorderVisible  
 かどうかは、コントロールの境界線を表示するかを示すフラグの状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbBorderVisible*  
 フラグの状態を受け取る変数。 TRUE は、コントロールの境界線が表示されていることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_borderwidth"></a>  CStockPropImpl::get_BorderWidth  
 コントロールの境界線の幅を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnBorderWidth*  
 コントロールの境界線の幅を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_caption"></a>  CStockPropImpl::get_Caption  
 オブジェクトのキャプションで指定したテキストを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstrCaption*  
 コントロールに表示されるテキストです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_drawmode"></a>  CStockPropImpl::get_DrawMode  
 XOR ペン、色の反転など、コントロールの描画モードを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnDrawMode*  
 コントロールの描画モードを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_drawstyle"></a>  CStockPropImpl::get_DrawStyle  
 実線、破線、点線などのコントロールの描画スタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnDrawStyle*  
 コントロールの描画スタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_drawwidth"></a>  CStockPropImpl::get_DrawWidth  
 このメソッドを呼び出して、描画幅 (ピクセル単位)、コントロールの描画メソッドで使用されるを取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnDrawWidth*  
 受け取る変数、コントロールの幅の値 (ピクセル単位)。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_enabled"></a>  CStockPropImpl::get_Enabled  
 このメソッドを呼び出して、コントロールが有効になっているかどうかを示すフラグの状態を取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbEnabled`  
 フラグの状態を受け取る変数。 TRUE は、コントロールが有効になっていることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_fillcolor"></a>  CStockPropImpl::get_FillColor  
 コントロールの塗りつぶしの色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrFillColor*  
 コントロールの塗りつぶしの色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_fillstyle"></a>  CStockPropImpl::get_FillStyle  
 純色、透明、ハッチなどのコントロールの塗りつぶしのスタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnFillStyle*  
 コントロールの塗りつぶしのスタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_font"></a>  CStockPropImpl::get_Font  
 このメソッドを呼び出して、コントロールのフォント プロパティへのポインターを取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFont`  
 コントロールのフォント プロパティへのポインターを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_forecolor"></a>  CStockPropImpl::get_ForeColor  
 コントロールの前景色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrForeColor*  
 コントロールの前景の色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_hwnd"></a>  CStockPropImpl::get_HWND  
 コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `phWnd`  
 コントロールに関連付けられているウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_mouseicon"></a>  CStockPropImpl::get_MouseIcon  
 (アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppPicture`  
 グラフィックの画像のプロパティへのポインターを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_mousepointer"></a>  CStockPropImpl::get_MousePointer  
 マウス ポインターの上にマウスがコントロールでは、たとえばときに表示されます、矢印、間、または砂時計の種類を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnMousePointer*  
 マウス ポインターの型を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_picture"></a>  CStockPropImpl::get_Picture  
 このメソッドを呼び出して (アイコン、ビットマップまたはメタファイル) を表示する画像の画像のプロパティへのポインターを取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppPicture`  
 画像のプロパティへのポインターを受け取る変数。 参照してください[IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762)詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_readystate"></a>  CStockPropImpl::get_ReadyState  
 ロードまたはアンロードなどのコントロールの準備完了の状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnReadyState*  
 コントロールの準備完了状態を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_tabstop"></a>  CStockPropImpl::get_TabStop  
 このメソッドを呼び出して、コントロールがタブ ストップがかどうかかを示すフラグの状態を取得します。  
  
```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbTabStop*  
 フラグの状態を受け取る変数。 TRUE は、コントロールがタブ ストップことを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_text"></a>  CStockPropImpl::get_Text  
 コントロールに表示されるテキストを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstrText*  
 コントロールに表示されるテキストです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_valid"></a>  CStockPropImpl::getvalid  
 このメソッドを呼び出して、コントロールが有効かどうかを示すフラグの状態を取得します。  
  
```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbValid*  
 フラグの状態を受け取る変数。 TRUE は、コントロールが有効であることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="get_window"></a>  CStockPropImpl::get_Window  
 コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。 同じ[CStockPropImpl::get_HWND](#get_hwnd)です。  
  
```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `phWnd`  
 コントロールに関連付けられているウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_appearance"></a>  CStockPropImpl::put_Appearance  
 このメソッドを呼び出して、コントロールで使用してフラット、ペイント スタイルまたは 3D を設定します。  
  
```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAppearance`  
 コントロールによって使用される新しい描画スタイルです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_autosize"></a>  CStockPropImpl::put_AutoSize  
 コントロールが他のサイズを変更できないかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAutoSize*  
 コントロールが他の任意のサイズを変更できない場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_backcolor"></a>  CStockPropImpl::put_BackColor  
 コントロールの背景色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrBackColor*  
 新しいコントロールの背景の色。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_backstyle"></a>  CStockPropImpl::put_BackStyle  
 コントロールの背景のスタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBackStyle*  
 新しいコントロールの背景のスタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_bordercolor"></a>  CStockPropImpl::put_BorderColor  
 コントロールの境界線の色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrBorderColor*  
 新しい境界線の色。 OLE_COLOR データ型は内部的には、32 ビット長整数として表されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_borderstyle"></a>  CStockPropImpl::put_BorderStyle  
 コントロールの境界線のスタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBorderStyle*  
 新しい境界線スタイルです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_bordervisible"></a>  CStockPropImpl::put_BorderVisible  
 かどうかは、コントロールの境界線を表示するかを示すフラグの値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 *bBorderVisible*  
 罫線を表示する場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_borderwidth"></a>  CStockPropImpl::put_BorderWidth  
 コントロールの境界線の幅を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBorderWidth`  
 新しいコントロールの境界線の幅。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_caption"></a>  CStockPropImpl::put_Caption  
 コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrCaption*  
 コントロールに表示されるテキストです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_drawmode"></a>  CStockPropImpl::put_DrawMode  
 XOR ペン、色の反転など、コントロールの描画モードを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawMode`  
 コントロールの新しいの描画モード。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_drawstyle"></a>  CStockPropImpl::put_DrawStyle  
 実線、破線、点線などのコントロールの描画スタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawStyle*  
 コントロールの新しい描画スタイルです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_drawwidth"></a>  CStockPropImpl::put_DrawWidth  
 幅 (ピクセル単位)、コントロールの描画メソッドで使用されるを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawWidth*  
 コントロールによって使用される新しい幅には、メソッドの描画します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_enabled"></a>  CStockPropImpl::put_Enabled  
 コントロールが有効になっているかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnabled`  
 コントロールが有効になっている場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_fillcolor"></a>  CStockPropImpl::put_FillColor  
 コントロールの塗りつぶしの色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrFillColor*  
 コントロールの新しい塗りつぶしの色。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_fillstyle"></a>  CStockPropImpl::put_FillStyle  
 純色、透明で、またはのクロスハッチなどのコントロールの塗りつぶしのスタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFillStyle*  
 コントロールの新しい塗りつぶしのスタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_font"></a>  付きます  
 コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 コントロールのフォント プロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_forecolor"></a>  CStockPropImpl::put_ForeColor  
 コントロールの前景の色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrForeColor*  
 コントロールの新しい前景色。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_hwnd"></a>  CStockPropImpl::put_HWND  
 このメソッドは、E_FAIL を返します。  
  
```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```  
  
### <a name="parameters"></a>パラメーター  
 */\* hWnd \*/*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 E_FAIL を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ ハンドルは、読み取り専用値です。  
  
##  <a name="put_mouseicon"></a>  付きます  
 (アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 グラフィックの画像のプロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_mousepointer"></a>  CStockPropImpl::put_MousePointer  
 マウス ポインターの上にマウスがコントロールでは、たとえばときに表示されます、矢印、間、または砂時計の種類を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMousePointer*  
 マウス ポインターの型。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_picture"></a>  付きます  
 (アイコン、ビットマップまたはメタファイル) を表示する画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 画像のプロパティへのポインター。 参照してください[IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762)詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_readystate"></a>  CStockPropImpl::put_ReadyState  
 ロードまたはアンロードなどのコントロールの準備完了の状態を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *nReadyState*  
 コントロールの準備完了状態。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_tabstop"></a>  CStockPropImpl::put_TabStop  
 コントロールがタブ ストップがかどうかかを示すフラグを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```  
  
### <a name="parameters"></a>パラメーター  
 *bTabStop*  
 コントロールがタブの停止の場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_text"></a>  CStockPropImpl::put_Text  
 コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrText`  
 コントロールに表示されるテキストです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_valid"></a>  CStockPropImpl::putvalid  
 コントロールが有効かどうかを示すフラグを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```  
  
### <a name="parameters"></a>パラメーター  
 *bValid*  
 コントロールが有効な場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="put_window"></a>  CStockPropImpl::put_Window  
 このメソッドを呼び出す[CStockPropImpl::put_HWND](#put_hwnd)E_FAIL が返されます。  
  
```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 ウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 E_FAIL を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ ハンドルは、読み取り専用値です。  
  
##  <a name="putref_font"></a>  CStockPropImpl::putref_Font  
 参照カウントが、コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 コントロールのフォント プロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 同じ[付きます](#put_font)、ですが、参照カウントをインクリメントします。  
  
##  <a name="putref_mouseicon"></a>  CStockPropImpl::putref_MouseIcon  
 参照カウントを持つ (アイコン、ビットマップまたはメタファイル)、コントロールの上にマウスが表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 グラフィックの画像のプロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 同じ[付きます](#put_mouseicon)、ですが、参照カウントをインクリメントします。  
  
##  <a name="putref_picture"></a>  CStockPropImpl::putref_Picture  
 参照カウントを持つ (アイコン、ビットマップまたはメタファイル)、表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 画像のプロパティへのポインター。 参照してください[IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762)詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 同じ[付きます](#put_picture)、ですが、参照カウントをインクリメントします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)
