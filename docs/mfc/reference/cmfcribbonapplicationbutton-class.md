---
title: CMFCRibbonApplicationButton クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17efa63488a736089c988e6cfbb7bd97330816aa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701390"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton クラス
アプリケーション ウィンドウの左上隅に表示される特殊なボタンを実装します。 このボタンがクリックされると、通常は、一般的な **[ファイル]** メニューのコマンド ( **[開く]**、 **[上書き保存]**、 **[終了]** など) を含むメニューが開かれます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|`CMFCRibbonApplicationButton` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonApplicationButton::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonApplicationButton::SetImage](#setimage)|リボン アプリケーション ボタンにイメージを割り当てます。|  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonApplicationButton`クラス。 例では、アプリケーションのボタンにイメージを割り当てる方法と、ツールヒントを設定する方法を示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../visual-cpp-samples.md)」の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonBar.h  
  
##  <a name="cmfcribbonapplicationbutton"></a>  CMFCRibbonApplicationButton::CMFCRibbonApplicationButton  
 構築し、初期化、 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)オブジェクト。  
  
```  
CMFCRibbonApplicationButton();  
CMFCRibbonApplicationButton(UINT uiBmpResID);  
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>パラメーター  
 *uiBmpResID*  
 アプリケーション ボタンに表示するイメージのリソース ID。  
  
 *hBmp*  
 アプリケーション ボタンを表示するビットマップへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 リボン アプリケーション ボタンは、アプリケーション ウィンドウの左上隅に配置されている特殊なボタンです。 アプリケーションが通常を含む一般的なメニューを開くユーザーには、このボタンがクリックすると、**ファイル**などのコマンド**オープン**、**保存**、および**終了**.  
  
##  <a name="setimage"></a>  CMFCRibbonApplicationButton::SetImage  
 アプリケーション ボタンにイメージを割り当てます。  
  
```  
void SetImage(UINT uiBmpResID);  
void SetImage(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>パラメーター  
*uiBmpResID*<br/>
[in]アプリケーション ボタンに表示するイメージのリソース ID。  
  
*hBmp*<br/>
[in]アプリケーション ボタンを表示するビットマップへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、ボタンを作成した後、リボン アプリケーション ボタンを新しいイメージを割り当てます。 アプリケーション ボタンは、アプリケーション ウィンドウの左上隅にあります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)
