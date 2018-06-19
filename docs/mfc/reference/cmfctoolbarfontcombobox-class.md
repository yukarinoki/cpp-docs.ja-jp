---
title: CMFCToolBarFontComboBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea8f05c20c3a3276f51b4267b6763831dc23eacf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373528"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox クラス
ユーザーがシステム フォントの一覧からフォントを選択できるコンボ ボックス コントロールを含むツール バー ボタンです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|`CMFCToolBarFontComboBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|ポインターを返します、`CMFCFontInfo`コンボ ボックスで指定したインデックスのオブジェクト。|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|フォントの名前またはフォントのプレフィックスと文字セットは、いずれかに従ってフォント コンボ ボックスでフォントを選択します。|  
  
### <a name="data-members"></a>データ メンバー  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 フォント コンボ ボックス内の文字の高さ。  
  
## <a name="remarks"></a>コメント  
 フォント コンボ ボックス ボタンをツールバーに追加するには、次の手順を実行します。  
  
1.  親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
2.  `CMFCToolBarFontComboBox` オブジェクトを構築します。  
  
3.  処理するメッセージ ハンドラーで、`AFX_WM_RESETTOOLBAR`メッセージで、元のボタンを使用して、新しいコンボ ボックス ボタンを置き換える[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)です。  
  
4.  使用して、ドキュメント内のフォント コンボ ボックスで選択されているフォントの同期、 [CMFCToolBarFontComboBox::SetFont](#setfont)メソッドです。  
  
 コンボ ボックスで選択したフォントを使用して、ドキュメントのフォントを同期するために使用して、 [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)選択したフォントの属性を取得し、それらの属性を使用して作成する方法、 [CFont クラス](../../mfc/reference/cfont-class.md)オブジェクト。  
  
 フォント コンボ ボックス ボタンは、Win32 関数を呼び出して[EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620)をシステムに使用できる画面およびプリンター フォントを決定します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
 構築、 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)オブジェクト。  
  
```  
public:  
CMFCToolBarFontComboBox(
    UINT uiID,  
    int iImage,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    DWORD dwStyle = CBS_DROPDOWN,  
    int iWidth = 0,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);

 
protected:  
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,  
    int nFontType,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily);  
  
CMFCToolBarFontComboBox();
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 コンボ ボックスのコマンド ID。  
  
 [入力] `iImage`  
 ツール バー イメージの 0 から始まるインデックス。 イメージが格納されて、 [CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトを[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスを保持します。  
  
 [入力] `nFontType`  
 コンボ ボックスに表示されるフォントの種類。 このパラメーターは、次の値の組み合わせ (論理 OR) を指定できます。  
  
 DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [入力] `nCharSet`  
 DEFAULT_CHARSET、コンボ ボックスに設定するには、すべての文字セットでフォントすべて一意な名前にはが含まれて 場合。 (同じ名前の 2 つのフォントがある場合は、コンボ ボックスが含まれていますうちの 1 つです。)場合は、コンボ ボックス、有効な文字セット値に設定するには、指定された文字セット内のフォントのみが含まれています。 参照してください[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)可能な文字の一覧についてを設定します。  
  
 [入力] `dwStyle`  
 コンボ ボックスのスタイルです。 (を参照してください[コンボ ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))  
  
 [入力] `iWidth`  
 エディット コントロールのピクセル単位の幅。  
  
 [入力] `nPitchAndFamily`  
 DEFAULT_PITCH、コンボ ボックスに設定するには、ピッチに関係なくフォントが含まれて 場合。 かどうか FIXED_PITCH または VARIABLE_PITCH に設定して、コンボ ボックス フォントのみを含む、ピッチ タイプにします。 フォント ファミリに基づいたフィルター処理は現在サポートされていません。  
  
 [出力] `pLstFontsExternal`  
 ポインター、 [CObList クラス](../../mfc/reference/coblist-class.md)使用できるフォントを格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 通常、`CMFCToolBarFontComboBox`オブジェクトは、単一の共有に使用できるフォントの一覧を格納`CObList`オブジェクト。 有効なポインターを指定するし、コンス トラクターの 2 番目のオーバー ロードを使用して`pLstFontsExternal`、その`CMFCToolBarFontComboBox`オブジェクトがいっぱいに代わりに、`CObList`を`pLstFontsExternal`使用可能なフォントを持つを指します。  
  
### <a name="example"></a>例  
 次の例で作成する方法、`CMFCToolBarFontComboBox`オブジェクト。 このコード スニペットは、 [Word パッド サンプル](../../visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc  
 ポインターを返します、`CMFCFontInfo`コンボ ボックスで指定したインデックスのオブジェクト。  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 コンボ ボックスの項目の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMFCFontInfo`オブジェクト。 場合`iIndex`、有効な項目のインデックスが指定されていません、戻り値は`NULL`します。  
  
##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight  
 コンボ ボックスがオーナー描画スタイルを持つ場合のフォント コンボ ボックス内の文字のピクセル単位の高さを指定します。  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>コメント  
 場合、`m_nFontHeight`変数が 0 の場合に応じて既定のフォント コンボ ボックスの高さが自動的に計算されます。 高さには、ベースラインより上の文字の上昇とベースラインの下にある文字のディセントの両方が含まれています。  
  
##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont  
 フォントの名前と文字に従ってフォント コンボ ボックスのフォント設定を選択しますが、パラメーターで指定されます。  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszName`  
 フォントの名前またはプレフィックスを指定します。  
  
 [入力] `nCharSet`  
 文字セットを指定します。  
  
 [入力] `bExact`  
 指定するかどうか`lpszName`フォント名またはフォントのプレフィックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 フォントが正常に選択されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bExact`は`TRUE`、このメソッドは、として指定した名前と一致するフォントを選択`lpszName`です。 場合`bExact`は`FALSE`、このメソッドの選択として指定されたテキストで始まるフォント`lpszName`として指定した文字セットを使用して`nCharSet`です。 場合`nCharSet`設定されている DEFAULT_CHARSET に、文字セットはされ、無視されたのみ`lpszName`フォントを選択するために使用されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)



