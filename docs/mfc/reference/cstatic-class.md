---
title: CStatic クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
dev_langs:
- C++
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc7a236b8a1dfc8877bc094641d26163f735a3e
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122770"
---
# <a name="cstatic-class"></a>CStatic クラス
Windows のスタティック コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|`CStatic` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStatic::Create](#create)|Windows のスタティック コントロールを作成し、それにアタッチ、`CStatic`オブジェクト。|  
|[CStatic::DrawItem](#drawitem)|オーナー描画スタティック コントロールを描画するためにオーバーライドします。|  
|[CStatic::GetBitmap](#getbitmap)|以前のビットマップのハンドルを取得[SetBitmap](#setbitmap)です。|  
|[CStatic::GetCursor](#getcursor)|カーソルのイメージのハンドルが以前に設定と取得[以前](#setcursor)です。|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|以前拡張メタファイルのハンドルを取得[SetEnhMetaFile](#setenhmetafile)です。|  
|[CStatic::GetIcon](#geticon)|既に設定アイコンのハンドルを取得[SetIcon](#seticon)です。|  
|[CStatic::SetBitmap](#setbitmap)|静的コントロールに表示されるビットマップを指定します。|  
|[CStatic::SetCursor](#setcursor)|静的コントロールに表示されるカーソル イメージを指定します。|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|静的コントロールに表示される拡張メタファイルを指定します。|  
|[CStatic::SetIcon](#seticon)|静的コントロールに表示されるアイコンを指定します。|  
  
## <a name="remarks"></a>Remarks  
 静的なコントロールは、テキスト文字列、ボックス、四角形、アイコン、カーソル、ビットマップ、または拡張メタファイルを表示します。 これは、ラベル付け、ボックス、またはその他のコントロールを個別に使用できます。 静的コントロール通常の入力を受け取らない用意されていません。ただし、SS_NOTIFY スタイルを使用して作成された場合にマウス クリックの親に通知できます。  
  
 2 つの手順では、スタティック コントロールを作成します。 最初に、構築するコンス トラクターを呼び出す、`CStatic`オブジェクト、し、呼び出し、[作成](#create)コントロールを作成し、静的アタッチにメンバー関数、`CStatic`オブジェクト。  
  
 作成する場合、 `CStatic` (ダイアログ リソースを使って)、ダイアログ ボックス内のオブジェクト、 `CStatic`  ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CStatic`ウィンドウ内でオブジェクトを破棄しても必要があります。 A`CStatic`ウィンドウ内のスタックで作成されるオブジェクトが自動的に破棄します。 作成する場合、`CStatic`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を関連付けし終わったら破棄するオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="create"></a>  CStatic::Create  
 Windows のスタティック コントロールを作成し、それにアタッチ、`CStatic`オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszText,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID = 0xffff);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 コントロール内に配置するテキストを指定します。 NULL の場合、テキスト表示されません。  
  
 *dwStyle*  
 静的コントロールのウィンドウ スタイルを指定します。 任意の組み合わせを適用[静的コントロール スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles)コントロールにします。  
  
 *rect*  
 静的コントロールのサイズと位置を指定します。 いずれかになります、`RECT`構造体、または`CRect`オブジェクト。  
  
 *pParentWnd*  
 指定します、`CStatic`親ウィンドウで、通常、`CDialog`オブジェクト。 NULL は指定できません。  
  
 *nID*  
 静的コントロールのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築、 `CStatic` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出す`CStatic`、まず`Create`、Windows のスタティック コントロールを作成しにアタッチする、`CStatic`オブジェクト。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)静的コントロールに。  
  
- WS_CHILD 常に  
  
- WS_VISIBLE 通常  
  
- WS_DISABLED ことはほとんどありません。  
  
 スタティック コントロールのビットマップ、カーソル、アイコン、またはメタファイルを表示する場合は、次のいずれかを適用する必要があります[静的コントロール スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles):  
  
- SS_BITMAP は、ビットマップをこのスタイルを使用します。  
  
- SS_ICON は、カーソル、アイコン、このスタイルを使用します。  
  
- SS_ENHMETAFILE 拡張メタファイルでこのスタイルを使用します。  
  
 カーソル、ビットマップ、アイコンのすることも次の形式を使用します。  
  
- 静的コントロールにイメージの中央に SS_CENTERIMAGE を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>  CStatic::CStatic  
 `CStatic` オブジェクトを構築します。  
  
```  
CStatic();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CStatic::DrawItem  
 オーナー描画スタティック コントロールを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDrawItemStruct*  
 ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)構造体。 構造体には、描画される項目および必要な図面の種類に関する情報が含まれています。  
  
### <a name="remarks"></a>Remarks  
 オーナー描画の描画を実装するには、この関数をオーバーライド`CStatic`(コントロールにスタイル SS_OWNERDRAW) オブジェクト。  
  
##  <a name="getbitmap"></a>  CStatic::GetBitmap  
 以前、ビットマップのハンドルを取得[SetBitmap](#setbitmap)、つまりに関連付けられている`CStatic`です。  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のビットマップ、またはビットマップが設定されていない場合は NULL へのハンドル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>  CStatic::GetCursor  
 以前、カーソルのハンドルを取得[以前](#setcursor)、つまりに関連付けられている`CStatic`です。  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>戻り値  
 現在のカーソルまたはカーソルが設定されていない場合は NULL へのハンドル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile  
 以前は、拡張メタファイルのハンドルを取得[SetEnhMetafile](#setenhmetafile)、つまりに関連付けられている`CStatic`です。  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の拡張メタファイルまたは拡張メタファイルが設定されていない場合は NULL へのハンドル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>  CStatic::GetIcon  
 以前のアイコンのハンドルを取得[SetIcon](#seticon)、つまりに関連付けられている`CStatic`です。  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のアイコンまたはアイコンが設定されていない場合は NULL へのハンドル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>  CStatic::SetBitmap  
 静的コントロールに新しいビットマップを関連付けます。  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 *hBitmap*  
 静的コントロールに描画されるビットマップのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 以前が関連付けられている静的コントロール、または NULL スタティック コントロールに関連付けられたビットマップができない場合、ビットマップのハンドル。  
  
### <a name="remarks"></a>Remarks  
 ビットマップは、静的コントロールに自動的に描画されます。 既定が左上隅で描画され、スタティック コントロールは、ビットマップのサイズを変更する場合は。  
  
 さまざまなウィンドウや静的コントロール スタイル (これらなど) を使用できます。  
  
-   SS_BITMAP は、ビットマップを常にこのスタイルを使用します。  
  
-   静的コントロールにイメージの中央に SS_CENTERIMAGE を使用します。 イメージがスタティック コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域は、ビットマップの左上隅にあるピクセルの色で入力されます。  
  
-   MFC クラスを提供する`CBitmap`はより Win32 を呼び出すだけよりビットマップ イメージに機能する必要があるときに使用できる`LoadBitmap`です。 `CBitmap`、協力でよく使用されて、GDI オブジェクトの 1 つの種類が含まれている`CStatic`、これは、`CWnd`が静的なコントロールとしてグラフィック オブジェクトを表示するために使用されるクラスです。  
  
 `CImage` ATL と MFC クラスをデバイスに依存しないビットマップ (DIB) を簡単に操作することができます。 詳細については、次を参照してください。 [CImage クラス](../../atl-mfc-shared/reference/cimage-class.md)です。  
  
-   一般的な使用方法が提供することです`CStatic::SetBitmap`GDI オブジェクトの HBITMAP 演算子によって返される、`CBitmap`または`CImage`オブジェクト。 これを行うコードでは、次の行に似ています。  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
次の例では、2 つ作成されます`CStatic`ヒープのオブジェクト。 次に、ビットマップを使用してシステムのいずれか、`CBitmap::LoadOEMBitmap`およびファイルを使用してから、その他の`CImage::Load`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>  CStatic::SetCursor  
 静的のコントロールに新しいカーソル イメージを関連付けます。  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>パラメーター  
 *hCursor*  
 静的コントロールに描画されるカーソルのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 静的コントロールに関連付けられたカーソルがない場合のスタティック コントロール、または NULL に以前関連付けられているカーソルのハンドルです。  
  
### <a name="remarks"></a>Remarks  
 カーソルは、静的コントロールに自動的に描画されます。 既定が左上隅で描画され、静的コントロールは、カーソルのサイズに変更されます。  
  
 さまざまなウィンドウや静的コントロール スタイル、次のようを使用することができます。  
  
- SS_ICON はカーソル、アイコン、常にこのスタイルを使用します。  
  
- 静的コントロールの中央に SS_CENTERIMAGE 使用します。 イメージがスタティック コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域はスタティック コントロールの背景色で入力します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile  
 静的コントロールには、新しい拡張メタファイル イメージを関連付けます。  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了しました。*  
 静的コントロールに描画するメタファイルのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 静的コントロールに関連付けられた拡張メタファイルがない場合、スタティック コントロール、または NULL に関連付けた拡張メタファイルのハンドル。  
  
### <a name="remarks"></a>Remarks  
 拡張メタファイルは、スタティック コントロールに自動的に描画されます。 拡張メタファイルは、スタティック コントロールのサイズに合わせてスケーリングされます。  
  
 さまざまなウィンドウや静的コントロール スタイル、次のようを使用することができます。  
  
- SS_ENHMETAFILE を使用して常にこのスタイルの拡張メタファイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>  CStatic::SetIcon  
 静的のコントロールに新しいアイコン イメージを関連付けます。  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 *hIcon*  
 静的コントロールに描画されるアイコンのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 静的コントロールに関連付けられたアイコンがない場合のスタティック コントロール、または NULL に以前関連付けられているアイコンのハンドル。  
  
### <a name="remarks"></a>Remarks  
 アイコンは、静的コントロールに自動的に描画されます。 既定が左上隅で描画され、スタティック コントロールは、アイコンのサイズを変更する場合は。  
  
 さまざまなウィンドウや静的コントロール スタイル、次のようを使用することができます。  
  
- SS_ICON はカーソル、アイコン、常にこのスタイルを使用します。  
  
- 静的コントロールの中央に SS_CENTERIMAGE 使用します。 イメージがスタティック コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域はスタティック コントロールの背景色で入力します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [関数クラス](../../mfc/reference/cscrollbar-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)
