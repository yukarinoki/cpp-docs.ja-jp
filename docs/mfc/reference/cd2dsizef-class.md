---
title: CD2DSizeF クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0093c92604013e4c1aef4046f244d7bcd3f71958
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353326"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF クラス
D2D1_SIZE_F のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|オーバーロードされます。 構築、`CD2DSizeF`オブジェクトから`D2D1_SIZE_F`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSizeF::IsNull](#isnull)|返します、`boolean`を式に有効なデータがないかどうかを示す値 ( `null`)。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSizeF::operator CSize](#operator_csize)|変換`CD2DSizeF`に`CSize`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dsizef"></a>  CD2DSizeF::CD2DSizeF  
 CSize オブジェクトから CD2DSizeF オブジェクトを構築します。  
  
```  
CD2DSizeF(const CSize& size);  
CD2DSizeF(const D2D1_SIZE_F& size);  
  CD2DSizeF(const D2D1_SIZE_F* size);

 
CD2DSizeF(
    FLOAT cx = 0.,  
    FLOAT cy = 0.);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 ソースのサイズ  
  
 `cx`  
 元の幅  
  
 `cy`  
 元の高さ  
  
##  <a name="isnull"></a>  CD2DSizeF::IsNull  
 式に有効なデータ (Null) がないかどうかを示すブール値を返します。  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>戻り値  
 幅と高さは空以外の場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="operator_csize"></a>  CD2DSizeF::operator CSize  
 CD2DSizeF を CSize オブジェクトに変換します。  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>戻り値  
 D2D サイズの現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
