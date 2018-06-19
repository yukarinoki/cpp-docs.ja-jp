---
title: CD2DSizeU クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa7c42216f55479050812b559f533829d55162b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349936"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU クラス
D2D1_SIZE_U のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|オーバーロードされます。 構築、`CD2DSizeU`オブジェクトから`D2D1_SIZE_U`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSizeU::IsNull](#isnull)|返します、`boolean`を式に有効なデータがないかどうかを示す値 ( `null`)。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSizeU::operator CSize](#operator_csize)|変換`CD2DSizeU`に`CSize`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dsizeu"></a>  CD2DSizeU::CD2DSizeU  
 CSize オブジェクトから CD2DSizeU オブジェクトを構築します。  
  
```  
CD2DSizeU(const CSize& size);  
CD2DSizeU(const D2D1_SIZE_U& size);  
  CD2DSizeU(const D2D1_SIZE_U* size);

 
CD2DSizeU(
    UINT32 cx = 0,  
    UINT32 cy = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 ソースのサイズ  
  
 `cx`  
 元の幅  
  
 `cy`  
 元の高さ  
  
##  <a name="isnull"></a>  CD2DSizeU::IsNull  
 式に有効なデータ (Null) がないかどうかを示すブール値を返します。  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>戻り値  
 幅と高さは空以外の場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="operator_csize"></a>  CD2DSizeU::operator CSize  
 CD2DSizeU を CSize オブジェクトに変換します。  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>戻り値  
 D2D サイズの現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
