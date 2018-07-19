---
title: CComFakeCriticalSection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a042e52439579cfb1b4145b1691f5a00128754c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358616"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection クラス
このクラスと同じメソッドを提供する[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)は、クリティカル セクションは提供しません。  
  
## <a name="syntax"></a>構文  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|クリティカル セクションが存在しないために機能しません。|  
|[CComFakeCriticalSection::Lock](#lock)|クリティカル セクションが存在しないために機能しません。|  
|[CComFakeCriticalSection::Term](#term)|クリティカル セクションが存在しないために機能しません。|  
|[CComFakeCriticalSection::Unlock](#unlock)|クリティカル セクションが存在しないために機能しません。|  
  
## <a name="remarks"></a>コメント  
 `CComFakeCriticalSection` 内のメソッドをミラー化[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)です。 ただし、`CComFakeCriticalSection`に重要なセクションは行わないため、そのメソッドが何もしません。  
  
 通常、使用して`CComFakeCriticalSection`を通じて、`typedef`名前か、`AutoCriticalSection`または`CriticalSection`です。 使用する場合[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)、これらの両方の`typedef`名前参照`CComFakeCriticalSection`です。 使用する場合[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を参照する[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)と`CComCriticalSection`、それぞれします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="init"></a>  CComFakeCriticalSection::Init  
 クリティカル セクションが存在しないために機能しません。  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="lock"></a>  CComFakeCriticalSection::Lock  
 クリティカル セクションが存在しないために機能しません。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="term"></a>  CComFakeCriticalSection::Term  
 クリティカル セクションが存在しないために機能しません。  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock  
 クリティカル セクションが存在しないために機能しません。  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
