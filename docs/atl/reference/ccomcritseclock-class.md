---
title: CComCritSecLock クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b03d22a7daff614c560c7531143b718de7351c0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880252"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock クラス
このクラスは、ロックとクリティカル セクション オブジェクトをロック解除のためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>パラメーター  
 *TLock*  
 ロックおよびロック解除するオブジェクト。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|コンストラクターです。|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。|  
|[CComCritSecLock::Unlock](#unlock)|クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>Remarks  
 ロックおよびより安全な方法でオブジェクトをロック解除をこのクラスを使用して、 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)または[CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock  
 コンストラクターです。  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 クリティカル セクション オブジェクト。  
  
 *bInitialLock*  
 最初のロックの状態: **true**ロックされていることを意味します。  
  
### <a name="remarks"></a>Remarks  
 クリティカル セクション オブジェクトを初期化します。  
  
##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock  
 デストラクターです。  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Remarks  
 クリティカル セクション オブジェクトのロックを解除します。  
  
##  <a name="lock"></a>  CComCritSecLock::Lock  
 クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常にロックされた場合、S_OK またはエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 オブジェクトが既にロックされているデバッグ ビルドでアサート エラーが発生します。  
  
##  <a name="unlock"></a>  CComCritSecLock::Unlock  
 クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトは、既にロックされているが、デバッグ ビルドでアサート エラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)
