---
title: CDacl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2724eebd218cea2795d483351ef91b34c9f1bf39
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364771"
---
# <a name="cdacl-class"></a>CDacl クラス
このクラスは、DACL (随意アクセス制御リスト) 構造体のラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|コンストラクターです。|  
|[CDacl:: ~ CDacl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|許可される ACE (アクセス制御エントリ) を追加、`CDacl`オブジェクト。|  
|[CDacl::AddDeniedAce](#adddeniedace)|拒否された、ACE の追加、`CDacl`オブジェクト。|  
|[CDacl::GetAceCount](#getacecount)|Ace (アクセス制御エントリ) の数を返します、`CDacl`オブジェクト。|  
|[CDacl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) を削除、`CDacl`オブジェクト。|  
|[CDacl::RemoveAllAces](#removeallaces)|含まれている Ace のすべてを削除、`CDacl`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトのセキュリティ記述子には、DACL を含めることができます。 DACL には、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する 0 個以上の Ace (アクセス制御エントリ) が含まれています。 DACL が空の場合 (つまり、ある Ace が 0 個)、アクセスが明示的に付与されません、アクセスが暗黙的に拒否されるようにします。 ただし、オブジェクトのセキュリティ記述子は、DACL を持たない場合は、オブジェクトが保護されていないと、完全なアクセス権を持つすべてのユーザー。  
  
 オブジェクトの DACL を取得するには、は、オブジェクトの所有者であるか、READ_CONTROL オブジェクトへのアクセスがある必要があります。 オブジェクトの DACL を変更するには、WRITE_DAC オブジェクトへのアクセスが必要です。  
  
 作成、追加、削除、およびから Ace を削除する指定されたクラスのメソッドを使用して、`CDacl`オブジェクト。 関連項目[AtlGetDacl](security-global-functions.md#atlgetdacl)と[AtlSetDacl](security-global-functions.md#atlsetdacl)です。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="addallowedace"></a>  CDacl::AddAllowedAce  
 許可される ACE (アクセス制御エントリ) を追加、`CDacl`オブジェクト。  
  
```
bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 A [CSid](../../atl/reference/csid-class.md)オブジェクト。  
  
 `AccessMask`  
 許可されるにはアクセス権のマスクを指定します、指定された`CSid`オブジェクト。  
  
 `AceFlags`  
 ACE の継承を制御するビット フラグのセット。  
  
 `pObjectType`  
 オブジェクトの型。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。  
  
### <a name="return-value"></a>戻り値  
 返します**true**に ACE が追加された場合、`CDacl`オブジェクト、 **false**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 A`CDacl`オブジェクトには、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する 0 個以上の Ace (アクセス制御エントリ) が含まれています。 このメソッドへのアクセスを許可する ACE を追加、`CDacl`オブジェクト。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)で設定できるさまざまなフラグの詳細については、`AceFlags`パラメーター。  
  
##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce  
 拒否された ACE (アクセス制御エントリ) に追加、`CDacl`オブジェクト。  
  
```
bool AddDeniedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 `CSid` オブジェクト。  
  
 `AccessMask`  
 拒否するアクセス権のマスクを指定します、指定された`CSid`オブジェクト。  
  
 `AceFlags`  
 ACE の継承を制御するビット フラグのセット。 既定値は、メソッドの最初のフォームでは 0 です。  
  
 `pObjectType`  
 オブジェクトの型。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。  
  
### <a name="return-value"></a>戻り値  
 返します**true**に ACE が追加された場合、`CDacl`オブジェクト、 **false**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 A`CDacl`オブジェクトには、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する 0 個以上の Ace (アクセス制御エントリ) が含まれています。 このメソッドへのアクセスを拒否する ACE を追加、`CDacl`オブジェクト。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)で設定できるさまざまなフラグの詳細については、`AceFlags`パラメーター。  
  
##  <a name="cdacl"></a>  CDacl::CDacl  
 コンストラクターです。  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の**ACL** (アクセス制御リスト) 構造体。  
  
### <a name="remarks"></a>コメント  
 `CDacl`オブジェクトを必要に応じて作成する、既存を使用して**ACL**構造体。 だけを DACL (随意アクセス制御リスト) を確認することが重要と SACL ではありません (システム アクセス制御リスト) は、このパラメーターとして渡す必要があります。 デバッグ ビルドでは、SACL を渡すことにより、アサートされます。 リリース ビルドでは、SACL を渡すことにより (アクセス制御エントリ) の Ace は無視され、ACL でとエラーは発生しません。  
  
##  <a name="dtor"></a>  CDacl:: ~ CDacl  
 デストラクターです。  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターを使用して、オブジェクトのすべての Ace (アクセス制御エントリ) などで取得したリソースを解放[CDacl::RemoveAllAces](#removeallaces)です。  
  
##  <a name="getacecount"></a>  CDacl::GetAceCount  
 Ace (アクセス制御エントリ) の数を返します、`CDacl`オブジェクト。  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 含まれている Ace の数を返します、`CDacl`オブジェクト。  
  
##  <a name="operator_eq"></a>  CDacl::operator =  
 代入演算子。  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存のオブジェクトに割り当てる ACL (アクセス制御リスト)。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CDacl`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数には、DACL (随意アクセス制御リスト) を渡すだけことを確認する必要があります。 SACL (システム アクセス制御リスト) を渡すこの関数によってアサート デバッグ ビルドでがエラーが発生なしリリース ビルドでします。  
  
##  <a name="removeace"></a>  CDacl::RemoveAce  
 特定の ACE (アクセス制御エントリ) を削除、`CDacl`オブジェクト。  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する ACE エントリのインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドはから派生[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)です。  
  
##  <a name="removeallaces"></a>  CDacl::RemoveAllAces  
 含まれている Ace (アクセス制御エントリ) のすべてを削除、`CDacl`オブジェクト。  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>コメント  
 削除ごと**ACE** (アクセス制御エントリ) の構造 (存在する場合) で、`CDacl`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [CAcl クラス](../../atl/reference/cacl-class.md)   
 [Acl](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
