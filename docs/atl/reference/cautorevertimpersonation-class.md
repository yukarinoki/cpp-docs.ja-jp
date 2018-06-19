---
title: CAutoRevertImpersonation クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 942c446fc64bb7e4210bc82e21fc2511ae01503a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359508"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation クラス
このクラスは、 [CAccessToken](../../atl/reference/caccesstoken-class.md)スコープ外になったときにこの状態オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|構築、`CAutoRevertImpersonation`オブジェクト|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|アクセス トークンの偽装の復帰を自動化します。|  
|[CAutoRevertImpersonation::Detach](#detach)|自動偽装復帰をキャンセルします。|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|このオブジェクトに関連付けられている現在のトークンのアクセスを取得します。|  
  
## <a name="remarks"></a>コメント  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)プロセスまたはスレッドのセキュリティ コンテキストを記述し、Windows NT または Windows 2000 のシステムにログオンしている各ユーザーに割り当てられているオブジェクトです。 これらのアクセス トークンを表すことができます、`CAccessToken`クラスです。  
  
 アクセス トークンを偽装する必要があります。 便宜上、このクラスが指定されましたが、; のアクセス トークンの権限の借用は行いません自動併存 nonimpersonated 状態のみを実行します。 これは、アクセス トークンの偽装にはいくつかの方法を実行できるためです。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="attach"></a>  CAutoRevertImpersonation::Attach  
 アクセス トークンの偽装の復帰を自動化します。  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pAT`  
 アドレス、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトを自動的に元に戻す  
  
### <a name="remarks"></a>コメント  
 このメソッドは、場合にのみ使用する必要があります、 [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md)オブジェクトが NULL で作成された`CAccessToken`ポインター、または[デタッチ](#detach)以前に呼び出されています。 単純な状況では、このメソッドを使用する必要はありません。  
  
##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation  
 `CAutoRevertImpersonation` オブジェクトを構築します。  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pAT`  
 アドレス、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトを自動的に元に戻します。  
  
### <a name="remarks"></a>コメント  
 可能であればの作成前に、アクセス トークンの実際の権限借用を個別に実行する必要があります、`CAutoRevertImpersonation`オブジェクト。 この権限の借用は元に戻す自動的にすると、`CAutoRevertImpersonation`オブジェクトがスコープから外れます。  
  
##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>コメント  
 有効に現在権限借用を元に戻します、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトの構築時、またはを通じて提供される、[アタッチ](#attach)メソッドです。 ない場合は`CAccessToken`が関連付けられている、デストラクターも何も起こりません。  
  
##  <a name="detach"></a>  CAutoRevertImpersonation::Detach  
 自動偽装復帰をキャンセルします。  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 以前関連付けられているアドレス[CAccessToken](../../atl/reference/caccesstoken-class.md)アソシエーションが存在しない場合は null です。  
  
### <a name="remarks"></a>コメント  
 呼び出す**デタッチ**により、`CAutoRevertImpersonation`オブジェクトに対して有効に現在権限借用を元に戻すから、 [CAccessToken](../../atl/reference/caccesstoken-class.md)このオブジェクトに関連付けられているオブジェクト。 `CAutoRevertImpersonation` 効果なしで破棄またはできる、同じまたは別に再関連付け`CAccessToken`オブジェクトを使用して[アタッチ](#attach)です。  
  
##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken  
 このオブジェクトに関連付けられている現在のトークンのアクセスを取得します。  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>戻り値  
 以前関連付けられているアドレス[CAccessToken](../../atl/reference/caccesstoken-class.md)アソシエーションが存在しない場合は null です。  
  
### <a name="remarks"></a>コメント  
 権限借用のバージョンを再設定を含む目的でこのメソッドが呼び出された場合、`CAccessToken`オブジェクト、[デタッチ](#detach)メソッドを代わりに使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ATLSecurity サンプル](../../visual-cpp-samples.md)   
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [クラスの概要](../../atl/atl-class-overview.md)
