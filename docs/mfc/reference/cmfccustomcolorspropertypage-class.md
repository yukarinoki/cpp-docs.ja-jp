---
title: CMFCCustomColorsPropertyPage クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c02c2590e4143460a2cd89bb2b7e7e167c92c0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370810"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage クラス
色のダイアログ ボックスで作成した色を選択できるプロパティ ページを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCustomColorsPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|プロパティ ページの色要素を設定します。|  
  
### <a name="remarks"></a>コメント  
 `CMFCColorDialog`クラスでは、このクラスを使用してカスタムの色 ページを表示します。 詳細については`CMFCColorDialog`を参照してください[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)です。  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCCustomColorsPropertyPage`オブジェクトし、プロパティ ページの色要素を設定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcustomcolorspropertypage.h  
  
##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup  
 プロパティ ページの色要素を設定します。  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `R`|RGB 値の赤の要素。|  
|[入力] `G`|RGB 値の緑の成分。|  
|[入力] `B`|RGB 値の青のコンポーネント。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、現在の RGB と関連付けられている HLS (色合い、明度、および鮮やかさ) の色の値、プロパティ ページを更新します。 [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo)メソッドは、フレームワークは、色のダイアログ ボックスを初期化または、ユーザーがマウスの左ボタンを押したときにこのメソッドを呼び出します。 詳細については`CMFCColorDialog`を参照してください[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage クラス](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
