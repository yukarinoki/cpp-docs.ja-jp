---
title: CD2DResource クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
dev_langs:
- C++
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1848e0fe6d3e09ea4707279e83293ae2dc0feb64
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950678"
---
# <a name="cd2dresource-class"></a>CD2DResource クラス
ブラシ、レイヤー、テキストなどの D2D リソースの作成および管理インターフェイスを提供する抽象クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DResource : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DResource::CD2DResource](#cd2dresource)|CD2DResource オブジェクトを構築します。|  
|[CD2DResource:: ~ CD2DResource](#cd2dresource__~cd2dresource)|デストラクターです。 D2D リソース オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DResource::Create](#create)|CD2DResource を作成します。|  
|[CD2DResource::Destroy](#destroy)|CD2DResource オブジェクトを破棄します。|  
|[CD2DResource::IsValid](#isvalid)|リソースの有効性のチェック|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DResource::IsAutoDestroy](#isautodestroy)|チェック自動では、フラグを破棄します。|  
|[CD2DResource::ReCreate](#recreate)|CD2DResource を再作成されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|(CRenderTarget) の所有者によって destoyed されるリソースには|  
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|親 CRenderTarget へのポインター)|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CD2DResource`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dresource"></a>  CD2DResource:: ~ CD2DResource  
 デストラクターです。 D2D リソース オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DResource();
```  
  
##  <a name="cd2dresource"></a>  CD2DResource::CD2DResource  
 CD2DResource オブジェクトを構築します。  
  
```  
CD2DResource(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentTarget*  
 レンダー ターゲットへのポインター。  
  
 *bAutoDestroy*  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>  CD2DResource::Create  
 CD2DResource を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pRenderTarget*  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>  CD2DResource::Destroy  
 CD2DResource オブジェクトを破棄します。  
  
```  
virtual void Destroy() = 0;  
```  
  
##  <a name="isautodestroy"></a>  CD2DResource::IsAutoDestroy  
 チェック自動では、フラグを破棄します。  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>戻り値  
 その所有者によって、オブジェクトが破棄される場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="isvalid"></a>  CD2DResource::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_bisautodestroy"></a>  CD2DResource::m_bIsAutoDestroy  
 (CRenderTarget) の所有者によって destoyed されるリソースには  
  
```  
BOOL m_bIsAutoDestroy;  
```  
  
##  <a name="m_pparenttarget"></a>  CD2DResource::m_pParentTarget  
 親 CRenderTarget へのポインター)  
  
```  
CRenderTarget* m_pParentTarget;  
```  
  
##  <a name="recreate"></a>  CD2DResource::ReCreate  
 CD2DResource を再作成されます。  
  
```  
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRenderTarget*  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
