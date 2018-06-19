---
title: CComSafeDeleteCriticalSection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff637f9e307f2714cd351f3c6bcaf1e4b78342e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363860"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection クラス
このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|コンストラクターです。|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|作成し、クリティカル セクション オブジェクトを初期化します。|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|  
|[CComSafeDeleteCriticalSection::Term](#term)|クリティカル セクション オブジェクトによって使用されるシステム リソースを解放します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|フラグかどうか、内部**CRITICAL_SECTION**オブジェクトが初期化されています。|  
  
## <a name="remarks"></a>コメント  
 `CComSafeDeleteCriticalSection` クラスから派生[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)です。 ただし、`CComSafeDeleteCriticalSection`を超える追加の安全性のメカニズムを提供[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)です。  
  
 インスタンス`CComSafeDeleteCriticalSection`がスコープ外に出るか、明示的には、メモリから削除されると、基になるクリティカル セクション オブジェクトは自動的にクリーンアップ有効である場合。 さらに、 [CComSafeDeleteCriticalSection::Term](#term)基になるクリティカル セクション オブジェクトが割り当てられていないかが既にメモリから解放された場合、メソッドが正常に終了します。  
  
 参照してください[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)詳細については、クリティカル セクションのヘルパー クラス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 コンストラクターです。  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>コメント  
 セット、 [m_bInitialized](#m_binitialized)データ メンバーを**false**です。  
  
##  <a name="dtor"></a>  CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 デストラクターです。  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>コメント  
 内部解放**CRITICAL_SECTION**メモリからオブジェクトの場合、 [m_bInitialized](#m_binitialized)データ メンバーに設定されている**true**です。  
  
##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init  
 基本クラス実装を呼び出して[Init](/visualstudio/debugger/init)設定と[m_bInitialized](#m_binitialized)に**true**正常終了した場合。  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>戻り値  
 結果を返します[CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init)です。  
  
##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock  
基本クラス実装を呼び出して[ロック](ccomcriticalsection-class.md#lock)です。  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>戻り値  
 結果を返します[CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)です。  
  
### <a name="remarks"></a>コメント  
 この方法では、 [m_bInitialized](#m_binitialized)データ メンバーに設定されている**true**エントリ時にします。 この条件が満たされない場合、デバッグ ビルドでアサーションが生成されます。  
  
 関数の動作の詳細についてを参照してください[CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)です。  
  
##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized  
 フラグかどうか、内部**CRITICAL_SECTION**オブジェクトが初期化されています。  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>コメント  
 **M_bInitialized**データ メンバーが、基になるの有効性を追跡するために使用される**CRITICAL_SECTION**オブジェクトに関連付けられている、 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)クラスです。 基になる**CRITICAL_SECTION**オブジェクトは、このフラグに設定されていない場合、メモリから解放するのには試行されません**true**です。  
  
##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term  
 基本クラス実装を呼び出して[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)場合は、内部**CRITICAL_SECTION**オブジェクトが無効です。  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>戻り値  
 結果を返します[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)、または**S_OK**場合[m_bInitialized](#m_binitialized)に設定された**false**エントリ時にします。  
  
### <a name="remarks"></a>コメント  
 内部いなくてもこのメソッドを呼び出すには安全では**CRITICAL_SECTION**オブジェクトが無効です。 場合、このクラスのデストラクターはこのメソッドを呼び出して、 [m_bInitialized](#m_binitialized)データ メンバーに設定されている**true**です。  
  
## <a name="see-also"></a>関連項目  
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
