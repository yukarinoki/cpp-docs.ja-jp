---
title: CMFCToolBarFontSizeComboBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53f87dd55373599f8ab8394284a6271930b9fcd6
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037510"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox クラス
コンボ ボックス コントロールのフォント サイズを選択することができますを含むツールバー ボタンをクリックします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|選択したフォント サイズを返します。|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|指定したフォントのすべてのサポートされているフォント サイズでコンボ ボックスのリストを塗りつぶします。|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Twips のフォント サイズを設定します。|  
  
## <a name="remarks"></a>Remarks  
 使用することができます、`CMFCToolBarFontSizeComboBox`オブジェクトと共に、 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)フォントとフォント サイズを選択するユーザーを有効にするオブジェクト。  
  
 フォント コンボ ボックス ボタンを追加すると同様に、ツールバーにフォント サイズのコンボ ボックス ボタンを追加できます。 詳細については、次を参照してください。 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)です。  
  
 ユーザーが新しいフォントを選択すると、`CMFCToolBarFontComboBox`オブジェクトを使用してそのフォントのサポートされているサイズを使用してフォント サイズのコンボ ボックスを入力し、 [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)メソッドです。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarFontSizeComboBox`を構成するクラス、`CMFCToolBarFontSizeComboBox`オブジェクト。 この例では、テキスト ボックスからの長さ、フォント サイズを取得、サイズ、フォント コンボ ボックスに、指定されたフォントのすべての有効なサイズを塗りつぶすおよび twips 単位で、フォント サイズを指定する方法を示します。 このコード スニペットは、 [Word パッド サンプル](../../visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 `CMFCToolBarFontSizeComboBox` オブジェクトを構築します。  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize  
 フォント サイズのコンボ ボックスのテキスト ボックスからの長さ、フォント サイズを取得します。  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値が正の場合は、twips のフォント サイズ。 コンボ ボックスのテキスト ボックスが空の場合は-1 になります。 エラーが発生した場合は-2 を返します。  
  
##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 すべての有効なサイズ指定されたフォントのフォント サイズのコンボ ボックスで塗りつぶします。  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*strFontName*  
 フォント名を指定します。  
  
### <a name="remarks"></a>Remarks  
 などのフォント コンボ ボックス内の選択とフォント サイズのコンボ ボックスでは、間で同期するときは、この関数を呼び出して、 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)です。  
  
##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize  
 丸められますが、指定したサイズ (twips 単位) でポイント、および単位のサイズを最も近い値にコンボ ボックスで選択したサイズ。  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nSize*  
 設定するには、フォント サイズ (twips 単位) を指定します。  
  
### <a name="remarks"></a>Remarks  
 呼び出すことによって後で、前の有効なフォント サイズを取得することができます、 [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)



