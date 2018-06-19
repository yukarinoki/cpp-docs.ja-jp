---
title: CSacl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 116e66d36dde016ef902a0b345eec33e46177b6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363585"
---
# <a name="csacl-class"></a>CSacl クラス
このクラスは、SACL (システム アクセス制御リスト) 構造体のラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|コンストラクターです。|  
|[CSacl:: ~ CSacl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|監査アクセス制御エントリ (ACE) を追加、`CSacl`オブジェクト。|  
|[CSacl::GetAceCount](#getacecount)|アクセス制御エントリ (Ace) の数を返します、`CSacl`オブジェクト。|  
|[CSacl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) を削除、 **CSacl**オブジェクト。|  
|[CSacl::RemoveAllAces](#removeallaces)|含まれている Ace のすべてを削除、`CSacl`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 SACL には、ドメイン コント ローラーのセキュリティ イベント ログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (Ace) が含まれています。 SACL がドメイン コント ローラーへのアクセス試行が発生した場所にのみ、オブジェクトのレプリカが含まれているすべてのドメイン コント ローラーではなく、ログ エントリを生成することに注意してください。  
  
 を設定またはオブジェクトのセキュリティ記述子の SACL を取得するには、スレッドを要求するアクセス トークンで SE_SECURITY_NAME 特権を有効にする必要があります。 管理者グループにはこの権限が既定では、与えられておよびその他のユーザーまたはグループに許可されていることができます。 権限を持っている付与が必要とされるすべて: 権限によって定義された操作を実行することができます、前に、特権必要がありますで有効にするセキュリティのアクセス トークンを有効するためにします。 モデルは、特定のシステム操作に対してのみ有効にして、不要になったときに、無効にする特権を使用できます。 参照してください[AtlGetSacl](security-global-functions.md#atlgetsacl)と[AtlSetSacl](security-global-functions.md#atlsetsacl) SE_SECURITY_NAME の有効化の例についてはします。  
  
 追加、削除、作成、およびから Ace を削除する指定されたクラスのメソッドを使用して、 **SACL**オブジェクト。 関連項目[AtlGetSacl](security-global-functions.md#atlgetsacl)と[AtlSetSacl](security-global-functions.md#atlsetsacl)です。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="addauditace"></a>  CSacl::AddAuditAce  
 監査アクセス制御エントリ (ACE) を追加、`CSacl`オブジェクト。  
  
```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md)オブジェクト。  
  
 `AccessMask`  
 監査するアクセス権のマスクを指定します、指定された`CSid`オブジェクト。  
  
 `bSuccess`  
 許可されるアクセス試行を監査するかどうかを指定します。 監査を有効にします。 true の場合に、このフラグを設定します。それ以外の場合、false に設定します。  
  
 *bFailure*  
 拒否されたアクセス試行を監査するかどうかを指定します。 監査を有効にします。 true の場合に、このフラグを設定します。それ以外の場合、false に設定します。  
  
 `AceFlags`  
 ACE の継承を制御するビット フラグのセット。  
  
 `pObjectType`  
 オブジェクトの型。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。  
  
### <a name="return-value"></a>戻り値  
 返します**true**に ACE が追加された場合、`CSacl`オブジェクト、 **false**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 A`CSacl`オブジェクトには、セキュリティ イベント ログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (Ace) が含まれています。 このメソッドにそのような ACE を追加、`CSacl`オブジェクト。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)で設定できるさまざまなフラグの詳細については、`AceFlags`パラメーター。  
  
##  <a name="csacl"></a>  CSacl::CSacl  
 コンストラクターです。  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の**ACL** (アクセス制御リスト) 構造体。  
  
### <a name="remarks"></a>コメント  
 `CSacl`オブジェクトを必要に応じて作成する、既存を使用して**ACL**構造体。 このパラメーターは、システム アクセス制御リスト (SACL) と随意アクセス制御リスト (DACL) ではなくことを確認します。 DACL が指定される場合のデバッグ ビルドでは、アサーションが発生します。 リリース ビルドでは、DACL からすべてのエントリが無視されます。  
  
##  <a name="dtor"></a>  CSacl:: ~ CSacl  
 デストラクターです。  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、すべてのアクセス制御エントリ (Ace) を含む、オブジェクトが取得した任意のリソースを解放します。  
  
##  <a name="getacecount"></a>  CSacl::GetAceCount  
 アクセス制御エントリ (Ace) の数を返します、`CSacl`オブジェクト。  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 含まれている Ace の数を返します、`CSacl`オブジェクト。  
  
##  <a name="operator_eq"></a>  CSacl::operator =  
 代入演算子。  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 **ACL**を既存のオブジェクトに割り当て (アクセス制御リスト)。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CSacl`オブジェクト。 いることを確認、 **ACL**パラメーターは実際には、システム アクセス制御リスト (SACL) および随意アクセス制御リスト (DACL) ではなくです。 アサーションが発生すると、デバッグ ビルドとリリース ビルドでは、 **ACL**パラメーターは無視されます。  
  
##  <a name="removeace"></a>  CSacl::RemoveAce  
 特定の ACE (アクセス制御エントリ) を削除、 **CSacl**オブジェクト。  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する ACE エントリのインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドはから派生[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)です。  
  
##  <a name="removeallaces"></a>  CSacl::RemoveAllAces  
 格納されているアクセス制御エントリ (Ace) のすべてを削除、`CSacl`オブジェクト。  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>コメント  
 削除ごと**ACE**構造体 (存在する場合)、`CSacl`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CAcl クラス](../../atl/reference/cacl-class.md)   
 [Acl](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
