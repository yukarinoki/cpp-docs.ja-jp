---
title: CAcl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bab138d743dc3f5346ce15449c2a31b5b2484fd9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365342"
---
# <a name="cacl-class"></a>CAcl クラス
このクラスは、用のラッパー、 `ACL` (アクセス制御リスト) 構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAcl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|配列`ACCESS_MASK`s。|  
|[CAcl::CAceFlagArray](#caceflagarray)|配列`BYTE`s。|  
|[CAcl::CAceTypeArray](#cacetypearray)|配列`BYTE`s。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|コンストラクターです。|  
|[CAcl:: ~ CAcl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|アクセス制御の数のエントリ (ACE) のオブジェクトを返します。|  
|[CAcl::GetAclEntries](#getaclentries)|アクセス制御リスト (ACL) エントリを取得、`CAcl`オブジェクト。|  
|[CAcl::GetAclEntry](#getaclentry)|すべてのエントリに関する情報の取得、`CAcl`オブジェクト。|  
|[CAcl::GetLength](#getlength)|ACL の長さを返します。|  
|[CAcl::GetPACL](#getpacl)|PACL (ACL へのポインター) を返します。|  
|[CAcl::IsEmpty](#isempty)|テスト、`CAcl`エントリ オブジェクトです。|  
|[CAcl::IsNull](#isnull)|状態を返します、`CAcl`オブジェクト。|  
|[CAcl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) を削除、`CAcl`オブジェクト。|  
|[CAcl::RemoveAces](#removeaces)|すべての Ace (アクセス制御エントリ) を削除、`CAcl`に適用されている、指定された`CSid`です。|  
|[CAcl::SetEmpty](#setempty)|マーク、`CAcl`オブジェクト空として取得します。|  
|[CAcl::SetNull](#setnull)|マーク、`CAcl`オブジェクトとして`NULL`です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::operator const ACL *](#operator_const_acl__star)|キャスト、`CAcl`オブジェクトを`ACL`構造体。|  
|[CAcl::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 **ACL**構造体は、ACL (アクセス制御リスト) のヘッダー。 ACL には、0 個以上のシーケンシャル リストが含まれる[Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868) (アクセス制御エントリ)。 ACL 内の個々 の Ace の番号が 0 から*n-1*ここで、 *n* ACL 内の Ace の数です。 ACL を編集するには、アプリケーションは、インデックスを使用して ACL 内でアクセス制御エントリ (ACE) を参照します。  
  
 ACL の 2 つの種類があります。  
  
-   随意  
  
-   システム  
  
 随意 ACL は、オブジェクトの所有者によって制御されますか、与えられたユーザー **WRITE_DAC**オブジェクトへのアクセス。 オブジェクトを持つことができます、アクセスの特定のユーザーとグループを指定します。 たとえば、ファイルの所有者は、ユーザーおよびグループことや、ファイルへのアクセスを持つことはできませんを制御する随意 ACL を使用できます。  
  
 オブジェクトには、システム レベルのセキュリティ情報がシステムには、システム管理者によって制御される ACL の形式で、それに関連付けられていることもできます。 システム ACL は、オブジェクトにアクセスするために、試行を監査する、システム管理者を許可することができます。  
  
 詳細については、次を参照してください。、 [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) Windows SDK の説明。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray  
 ACCESS_MASK オブジェクトの配列。  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef は、アクセス制御エントリ (Ace) で使用されるアクセス権を格納するために使用する配列の型を指定します。  
  
##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray  
 バイトの配列。  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef は、アクセス制御エントリ (ACE) の種類に固有の制御フラグを定義するために使用する配列の型を指定します。 参照してください、 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)可能なフラグの完全な一覧を定義します。  
  
##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray  
 バイトの配列。  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef は、ACCESS_ALLOWED_ACE_TYPE または ACCESS_DENIED_ACE_TYPE など、アクセス制御エントリ (ACE) のオブジェクトの種類を定義するために使用する配列の型を指定します。 参照してください、 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)使用可能な型の完全な一覧を定義します。  
  
##  <a name="cacl"></a>  CAcl::CAcl  
 コンストラクターです。  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の `CAcl` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CAcl`オブジェクトを必要に応じて作成する、既存を使用して`CAcl`オブジェクト。  
  
##  <a name="dtor"></a>  CAcl:: ~ CAcl  
 デストラクターです。  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、オブジェクトが取得したすべてのリソースを解放します。  
  
##  <a name="getacecount"></a>  CAcl::GetAceCount  
 アクセス制御の数のエントリ (ACE) のオブジェクトを返します。  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 ACE のエントリの数を返します、`CAcl`オブジェクト。  
  
##  <a name="getaclentries"></a>  CAcl::GetAclEntries  
 アクセス制御リスト (ACL) エントリを取得、`CAcl`オブジェクト。  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSids`  
 配列へのポインター [CSid](../../atl/reference/csid-class.md)オブジェクト。  
  
 *pAccessMasks*  
 アクセス マスク。  
  
 *pAceTypes*  
 アクセス制御エントリ ( **ACE**) の種類。  
  
 *pAceFlags*  
 **ACE**フラグ。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって、配列パラメーターの詳細をすべて**ACE**に含まれているオブジェクト、`CAcl`オブジェクト。 その特定の配列の詳細が必要がない場合は、NULL を使用します。  
  
 つまりの最初の要素の互いに、各配列の内容が対応、`CAccessMaskArray`の最初の要素に対応する配列、`CSidArray`配列、およびなです。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) ACE 型とフラグの詳細についてはします。  
  
##  <a name="getaclentry"></a>  CAcl::GetAclEntry  
 すべてのアクセス制御リスト (ACL) 内のエントリに関する情報を取得します。  
  
```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得する ACL エントリのインデックスです。  
  
 `pSid`  
 [CSid](../../atl/reference/csid-class.md) ACL エントリを適用するオブジェクトします。  
  
 *pMask*  
 アクセス許可または拒否するアクセス許可を指定するマスク。  
  
 `pType`  
 ACE 型です。  
  
 `pFlags`  
 ACE のフラグです。  
  
 `pObjectType`  
 オブジェクトの型。 ACE は、オブジェクトの ACE がない場合、ACE のオブジェクトの種類が指定されていない場合または GUID_ に設定されます。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。 ACE は、オブジェクトの ACE がない場合、ACE の継承されたオブジェクトの種類が指定されていない場合または GUID_ に設定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドより多くの情報を提供する、個々 の ACE の情報をすべて取得されます[CAcl::GetAclEntries](#getaclentries)単独で使用できるようにします。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) ACE 型とフラグの詳細についてはします。  
  
##  <a name="getlength"></a>  CAcl::GetLength  
 アクセス制御リスト (ACL) の長さを返します。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 保持するために必要なバイト数で、必要な長さを返します、 **ACL**構造体。  
  
##  <a name="getpacl"></a>  CAcl::GetPACL  
 アクセス制御リスト (ACL) へのポインターを返します。  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、 **ACL**構造体。  
  
##  <a name="isempty"></a>  CAcl::IsEmpty  
 テスト、`CAcl`エントリ オブジェクトです。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します**true**場合、`CAcl`オブジェクトが NULL でないと、エントリが含まれていません。 返します**false**場合、`CAcl`オブジェクトが NULL であるか、または少なくとも 1 つのエントリが含まれています。  
  
##  <a name="isnull"></a>  CAcl::IsNull  
 状態を返します、`CAcl`オブジェクト。  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合、`CAcl`オブジェクトが NULL の場合、 **false**それ以外の場合。  
  
##  <a name="operator_const_acl__star"></a>  CAcl::operator const ACL *  
 キャスト、`CAcl`オブジェクトを**ACL** (アクセス制御リスト) 構造体。  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>コメント  
 アドレスを返します、 **ACL**構造体。  
  
##  <a name="operator_eq"></a>  CAcl::operator =  
 代入演算子。  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CAcl`を既存のオブジェクトに割り当てます。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CAcl`オブジェクト。  
  
##  <a name="removeace"></a>  CAcl::RemoveAce  
 特定の ACE (アクセス制御エントリ) を削除、 **CAcl**オブジェクト。  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する ACE エントリのインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドはから派生[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)です。  
  
##  <a name="removeaces"></a>  CAcl::RemoveAces  
 Alls Ace (アクセス制御エントリ) を削除、`CAcl`に適用されている、指定された`CSid`です。  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 `CSid` オブジェクトへの参照。  
  
##  <a name="setempty"></a>  CAcl::SetEmpty  
 マーク、`CAcl`オブジェクト空として取得します。  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CAcl`を空または NULL に設定できます。 2 つの状態は異なります。  
  
##  <a name="setnull"></a>  CAcl::SetNull  
 マーク、`CAcl`オブジェクトを NULL として。  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CAcl`を空または NULL に設定できます。 2 つの状態は異なります。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
