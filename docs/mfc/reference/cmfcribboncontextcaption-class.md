---
title: CMFCRibbonContextCaption クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2fa63de2a633b2c8a9fff975de6eaaae7cbb470c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption クラス
リボン カテゴリまたはコンテキスト カテゴリの最上位に表示される色付きのキャプションを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonContextCaption : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonContextCaption::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCRibbonContextCaption::GetColor](#getcolor)|キャプションの色を返します。|  
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||  
|`CMFCRibbonContextCaption::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 このクラスを直接インスタンス化することはできません。 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)クラス クラスを使用してこの内部的にリボン カテゴリに色を追加します。  
  
 リボン カテゴリの色を設定するには、呼び出す[cmfcribboncategory::settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)です。 コンテキスト カテゴリの色を設定するには、呼び出す[cmfcribbonbar::addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonBar.h  
  
##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor  
 キャプションの背景色を返します。  
  
```  
AFX_RibbonCategoryColor GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返される値には、次の列挙値のいずれかを指定できます。  
  
- `AFX_CategoryColor_None`  
  
- `AFX_CategoryColor_Red`  
  
- `AFX_CategoryColor_Orange`  
  
- `AFX_CategoryColor_Yellow`  
  
- `AFX_CategoryColor_Green`  
  
- `AFX_CategoryColor_Blue`  
  
- `AFX_CategoryColor_Indigo`  
  
- `AFX_CategoryColor_Violet`  
  
### <a name="remarks"></a>コメント  
 呼び出して、キャプションの色を設定することができます[cmfcribboncategory::settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)または[cmfcribbonbar::addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)です。  
  
##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX  
 カテゴリのリボン タブの右側のエッジの位置を取得します。  
  
```  
int GetRightTabX() const;  
```  
  
### <a name="return-value"></a>戻り値  
 それを囲む四角形の右側の X 値を返します、`CMFCRibbonCategory`オブジェクトのリボン タブまたはタブが切り捨てられる場合は-1 の値。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
