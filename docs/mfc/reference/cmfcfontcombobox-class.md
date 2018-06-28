---
title: CMFCFontComboBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9141dec6fdcb966dcdb664bb8dc090b50a10a614
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040000"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox クラス
`CMFCFontComboBox`クラスは、フォントの一覧を含むコンボ ボックス コントロールを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|`CMFCFontComboBox` オブジェクトを構築します。|  
|`CMFCFontComboBox::~CMFCFontComboBox`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|現在のフォント コンボ ボックス コントロールの並べ替えられたリスト ボックスに新しい項目の相対位置を決定するためにフレームワークによって呼び出されます。 (上書き[CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem))。|  
|`CMFCFontComboBox::DrawItem`|現在のフォント コンボ ボックス コントロールで、指定した項目を描画するためにフレームワークによって呼び出されます。 (上書き[CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem))。|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|現在選択されているフォントに関する情報を取得します。|  
|`CMFCFontComboBox::MeasureItem`|現在のフォント コンボ ボックス コントロールのリスト ボックスのサイズの Windows に通知するためにフレームワークによって呼び出されます。 (上書き[CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem))。|  
|`CMFCFontComboBox::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|  
|[CMFCFontComboBox::SelectFont](#selectfont)|フォント コンボ ボックスから、指定した条件に一致するフォントを選択します。|  
|[CMFCFontComboBox::Setup](#setup)|フォント コンボ ボックス内の項目のリストを初期化します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|フレームワークの現在のフォント コンボ ボックス内の項目のラベルの描画に使用するフォントを示します。|  
  
## <a name="remarks"></a>Remarks  
 使用する、 `CMFCFontComboBox`  ダイアログ ボックスでオブジェクトを追加、 `CMFCFontComboBox`  ダイアログ ボックス クラスに変数。 次に、 `OnInitDialog`  ダイアログ ボックスのクラス、呼び出しのメソッド、 [CMFCFontComboBox::Setup](#setup)コンボ ボックス コントロール内の項目のリストを初期化します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox  
 `CMFCFontComboBox` オブジェクトを構築します。  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont  
 現在選択されているフォントに関する情報を取得します。  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)フォントを表すオブジェクト。 できます`NULL`コンボ ボックスのフォントが選択されていない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont  
 フレームワークの現在のフォント コンボ ボックス内の項目のラベルの描画に使用するフォントを示します。  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバーを設定`TRUE`同じフォントを使用して、各項目のラベルを描画するために、フレームワークを送信するためです。 このメンバーを設定`FALSE`フレームワークの名前は、ラベルと同じフォントで各項目のラベルの描画に指示します。 このメンバーの既定値は`FALSE`します。  
  
##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont  
 フォント コンボ ボックスから、指定した条件に一致するフォントを選択します。  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDesc*  
 フォントの説明オブジェクトへのポインター。  
  
 [in]*lpszName*  
 フォント名を指定します。  
  
 [in]*nCharSet*  
 文字セットを指定します。 既定値は、DEFAULT_CHARSET です。 詳細については、次を参照してください。、`lfCharSet`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 説明オブジェクトの指定したフォントまたはフォント名と charset; フォント コンボ ボックス内の項目に一致する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、選択し、指定したフォントに対応するフォント コンボ ボックス内の項目にスクロールします。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`SelectFont`メソッドで、`CMFCFontComboBox`クラスです。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>  CMFCFontComboBox::Setup  
 フォント コンボ ボックス内の項目のリストを初期化します。  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nFontType*  
 フォントの種類を指定します。 既定値は、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE のビットごとの組み合わせ (OR) です。  
  
 [in]*nCharSet*  
 フォントの文字セットを指定します。 既定値は、DEFAULT_CHARSET です。  
  
 [in]*nPitchAndFamily*  
 フォントのピッチとファミリを指定します。 既定値は、DEFAULT_PITCH です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` フォント コンボ ボックスが正常に初期化される場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、指定したパラメーターに一致する現在インストールされているフォントを列挙する、フォント コンボ ボックスでそのフォント名を挿入してフォント コンボ ボックスを初期化します。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`Setup`メソッドで、`CMFCFontComboBox`クラスです。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)
