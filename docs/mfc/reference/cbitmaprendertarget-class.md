---
title: CBitmapRenderTarget クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0eece5c7ba74f523836ab5916b8817671dac287
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956753"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget クラス
ID2D1BitmapRenderTarget のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|CBitmapRenderTarget オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](#attach)|既存の接続オブジェクトを対象のインターフェイスを表示します。|  
|[CBitmapRenderTarget::Detach](#detach)|レンダー ターゲット インターフェイス オブジェクトからのデタッチします。|  
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|このレンダー ターゲットのビットマップを取得します。 返されるビットマップを描画操作に使用できます。|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|返します ID2D1BitmapRenderTarget インターフェイス|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|返します ID2D1BitmapRenderTarget インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget オブジェクトへのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 `CBitmapRenderTarget` 
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="attach"></a>  CBitmapRenderTarget::Attach  
 既存の接続オブジェクトを対象のインターフェイスを表示します。  
  
```  
void Attach(ID2D1BitmapRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 *pTarget*  
 既存のレンダー ターゲット インターフェイスです。 NULL をすることはできません。  
  
##  <a name="cbitmaprendertarget"></a>  CBitmapRenderTarget::CBitmapRenderTarget  
 CBitmapRenderTarget オブジェクトを構築します。  
  
```  
CBitmapRenderTarget();
```  
  
##  <a name="detach"></a>  CBitmapRenderTarget::Detach  
 レンダー ターゲット インターフェイス オブジェクトからのデタッチします。  
  
```  
ID2D1BitmapRenderTarget* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたへのポインターは、対象のインターフェイスをレンダリングします。  
  
##  <a name="getbitmap"></a>  CBitmapRenderTarget::GetBitmap  
 このレンダー ターゲットのビットマップを取得します。 返されるビットマップを描画操作に使用できます。  
  
```  
BOOL GetBitmap(CD2DBitmap& bitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 *ビットマップ*  
 このメソッドが戻るときに、このレンダー ターゲットに対する有効なビットマップが含まれています。 このビットマップを描画操作に使用できます。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="getbitmaprendertarget"></a>  CBitmapRenderTarget::GetBitmapRenderTarget  
 返します ID2D1BitmapRenderTarget インターフェイス  
  
```  
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1BitmapRenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="m_pbitmaprendertarget"></a>  CBitmapRenderTarget::m_pBitmapRenderTarget  
 ID2D1BitmapRenderTarget オブジェクトへのポインター。  
  
```  
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;  
```  
  
##  <a name="operator_id2d1bitmaprendertarget_star"></a>  CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *  
 返します ID2D1BitmapRenderTarget インターフェイス  
  
```  
operator ID2D1BitmapRenderTarget*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1BitmapRenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
