---
title: CSid クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
dev_langs:
- C++
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed55fd2286c3d6e37b59b16a06f43cc4efe55091
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366407"
---
# <a name="csid-class"></a>CSid クラス
このクラスは、用のラッパー、 `SID` (セキュリティ識別子) 構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSid
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|`CSid` オブジェクトの配列。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSid::CSid](#csid)|コンストラクターです。|  
|[CSid:: ~ CSid](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|関連付けられているアカウントの名前を返します、`CSid`オブジェクト。|  
|[CSid::Domain](#domain)|関連付けられているドメインの名前を返します、`CSid`オブジェクト。|  
|[CSid::EqualPrefix](#equalprefix)|テスト`SID`等しいかどうか (セキュリティ識別子) のプレフィックス。|  
|[CSid::GetLength](#getlength)|長さを返します、`CSid`オブジェクト。|  
|[CSid::GetPSID](#getpsid)|ポインターを返します、`SID`構造体。|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|ポインターを返します、 **SID_IDENTIFIER_AUTHORITY**構造体。|  
|[CSid::GetSubAuthority](#getsubauthority)|指定された副機関を返します、 **SID**構造体。|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|副機関の数を返します。|  
|[CSid::IsValid](#isvalid)|テスト、`CSid`の有効性のオブジェクト。|  
|[CSid::LoadAccount](#loadaccount)|更新プログラム、`CSid`指定して、アカウント名とドメイン、または既存のオブジェクト`SID`構造体。|  
|[CSid::Sid](#sid)|ID 文字列を返します。|  
|[CSid::SidNameUse](#sidnameuse)|状態の説明を返します、`CSid`オブジェクト。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|代入演算子。|  
|[演算子の const SID *](#operator_const_sid__star)|キャスト、`CSid`オブジェクトへのポインターを`SID`構造体。|  
  
### <a name="global-operators"></a>グローバル演算子  
  
|||  
|-|-|  
|[operator ==](#operator_eq_eq)|2 つのセキュリティ記述子オブジェクトの等価性をテストします。|  
|[operator !=](#operator_neq)|非等値を 2 つのセキュリティ記述子オブジェクトを調べます|  
|[演算子 \<](#operator_lt_)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 >](#operator_gt_)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 \<=](#operator_lt__eq)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
|[operator > =](#operator_gt__eq)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
  
## <a name="remarks"></a>コメント  
 `SID`構造体は、可変長の構造体のユーザーまたはグループを一意に識別するために使用します。  
  
 アプリケーションは変更しないでください、`SID`構造に直接が代わりには、このラッパー クラスで提供されるメソッドを使用します。 関連項目[AtlGetOwnerSid](security-global-functions.md#atlgetownersid)、 [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid)、 [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid)、および[AtlSetOwnerSid](security-global-functions.md#atlsetownersid)です。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="accountname"></a>  CSid::AccountName  
 関連付けられているアカウントの名前を返します、`CSid`オブジェクト。  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 返します、`LPCTSTR`アカウントの名前をポイントします。  
  
### <a name="remarks"></a>コメント  
 このメソッドが、指定した名前を検索しようとしています。 `SID` (セキュリティ識別子)。 詳細については、次を参照してください。 [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166)です。  
  
 アカウント名がない場合、`SID`を取れる`AccountName`空の文字列を返します。 これは、ネットワークのタイムアウトが原因でこのメソッドが、名前を検索する場合に発生します。 対応するアカウント名のないログオンなどのセキュリティ識別子にも発生`SID`ログオン セッションを識別します。  
  
##  <a name="csid"></a>  CSid::CSid  
 コンストラクターです。  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の`CSid`オブジェクトまたは`SID`(セキュリティ識別子) 構造体。  
  
 *IdentifierAuthority*  
 証明機関。  
  
 *nSubAuthorityCount*  
 副機関の数。  
  
 `pszAccountName`  
 アカウント名。  
  
 `pszSystem`  
 システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。  
  
 `pSid`  
 ポインター、`SID`構造体。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、`CSid`オブジェクト、内部データ メンバーに設定*SidTypeInvalid*、または、既存の設定をコピーして`CSid`、 `SID`、または既存のアカウントです。  
  
 コンス トラクターが初期化に失敗した場合にスローされます、 [CAtlException クラス](../../atl/reference/catlexception-class.md)です。  
  
##  <a name="dtor"></a>  CSid:: ~ CSid  
 デストラクターです。  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、オブジェクトが取得したすべてのリソースを解放します。  
  
##  <a name="csidarray"></a>  CSid::CSidArray  
 配列[CSid](../../atl/reference/csid-class.md)オブジェクト。  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef は、ACL (アクセス制御リスト) からのセキュリティ識別子を取得するために使用する配列の型を指定します。 参照してください[CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries)です。  
  
##  <a name="domain"></a>  CSid::Domain  
 関連付けられているドメインの名前を返します、`CSid`オブジェクト。  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 返します、`LPCTSTR`ドメイン をポイントします。  
  
### <a name="remarks"></a>コメント  
 このメソッドが、指定した名前を検索しようとしています。 `SID` (セキュリティ識別子)。 詳細については、次を参照してください。 [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166)です。  
  
 アカウント名がない場合、`SID`を取れる**ドメイン**空の文字列としてドメインを返します。 これは、ネットワークのタイムアウトが原因でこのメソッドが、名前を検索する場合に発生します。 対応するアカウント名のないログオンなどのセキュリティ識別子にも発生`SID`ログオン セッションを識別します。  
  
##  <a name="equalprefix"></a>  CSid::EqualPrefix  
 テスト`SID`等しいかどうか (セキュリティ識別子) のプレフィックス。  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `SID` (セキュリティ識別子) 構造体または`CSid`と比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**成功した場合、 **false**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 参照してください[EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621)詳細については、Windows SDK に含まれています。  
  
##  <a name="getlength"></a>  CSid::GetLength  
 長さを返します、`CSid`オブジェクト。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 バイトの長さを返します、`CSid`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 場合、`CSid`構造が無効、戻り値が定義されていません。 呼び出す前に`GetLength`を使用して、 [CSid::IsValid](#isvalid)ことを確認するメンバー関数`CSid`が無効です。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="getpsid"></a>  CSid::GetPSID  
 ポインターを返します、 `SID` (セキュリティ識別子) 構造体。  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 アドレスを返します、`CSid`オブジェクトの基になる`SID`構造体。  
  
##  <a name="getpsid_identifier_authority"></a>  CSid::GetPSID_IDENTIFIER_AUTHORITY  
 ポインターを返します、 **SID_IDENTIFIER_AUTHORITY**構造体。  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 アドレスが返される、メソッドが成功した場合、 **SID_IDENTIFIER_AUTHORITY**構造体。 失敗した場合、戻り値は定義されません。 場合に、エラーが発生する可能性があります、`CSid`オブジェクトが有効でない場合、 [CSid::IsValid](#isvalid)メソッドを返します。 **false**です。 関数は、`GetLastError`拡張エラー情報を呼び出すことができます。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="getsubauthority"></a>  CSid::GetSubAuthority  
 指定された副機関を返します、 `SID` (セキュリティ識別子) 構造体。  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nSubAuthority*  
 副機関。  
  
### <a name="return-value"></a>戻り値  
 によって参照される副機関を返します*nSubAuthority です。* 副機関の値は、相対識別子 (RID) です。  
  
### <a name="remarks"></a>コメント  
 *NSubAuthority*パラメーター メソッドが返す副機関配列要素を識別するインデックス値を指定します。 メソッドは、この値を検証テストを実行しません。 アプリケーションが呼び出すことができます[から](#getsubauthoritycount)値の許容範囲を検出します。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="getsubauthoritycount"></a>  CSid::GetSubAuthorityCount  
 副機関の数を返します。  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、副機関の数を返します。  
  
 メソッドが失敗した場合、戻り値は定義されません。 メソッドは失敗、`CSid`オブジェクトが無効です。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="isvalid"></a>  CSid::IsValid  
 テスト、`CSid`の有効性のオブジェクト。  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合、`CSid`オブジェクトが有効で**false**しない場合。 このメソッドの拡張エラー情報はありません。呼び出す必要はありません`GetLastError`です。  
  
### <a name="remarks"></a>コメント  
 `IsValid`メソッドは、検証、`CSid`リビジョン番号が、既知の範囲内であると副機関の数が最大値より小さいことを確認することによってオブジェクト。  
  
##  <a name="loadaccount"></a>  CSid::LoadAccount  
 指定されたアカウント名とドメイン、または既存の SID (セキュリティ識別子) 構造体で、`CSid` オブジェクトを更新します。  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszAccountName`  
 アカウント名。  
  
 `pszSystem`  
 システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。  
  
 `pSid`  
 ポインター、 [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx)構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**true**成功した場合、 **false**エラー発生時にします。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 `LoadAccount` は、指定された名前でセキュリティ識別子の検索を試行します。 参照してください[LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx)詳細についてはします。  
  
##  <a name="operator_eq"></a>  CSid::operator =  
 代入演算子。  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`に割り当てる、`CSid`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CSid`オブジェクト。  
  
##  <a name="operator_eq_eq"></a>  CSid::operator = =  
 2 つのセキュリティ記述子オブジェクトの等価性をテストします。  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、演算子 = = です。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、演算子 = = です。  
  
### <a name="return-value"></a>戻り値  
 **true**セキュリティ記述子が等しい場合は、それ以外の場合**false**です。  
  
##  <a name="operator_neq"></a>  CSid::operator! =  
 非等値を 2 つのセキュリティ記述子オブジェクトをテストします。  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**セキュリティ記述子等しくない場合、それ以外の場合**false**です。  
  
##  <a name="operator_lt"></a>  CSid::operator &lt;  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`はより小さい`rhs`それ以外の場合、 **false**です。  
  
##  <a name="operator_lt__eq"></a>  CSid::operator &lt;=  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`と同じかそれよりも少ない`rhs`それ以外の場合、 **false**です。  
  
##  <a name="operator_gt"></a>  CSid::operator &gt;  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`がより大きい`rhs`それ以外の場合、 **false**です。  
  
##  <a name="operator_gt__eq"></a>  CSid::operator &gt;=  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`がより大きいまたは等しい`rhs`それ以外の場合、 **false**です。  
  
##  <a name="operator_const_sid__star"></a>  CSid::operator const SID *  
 キャスト、`CSid`オブジェクトへのポインターを`SID`(セキュリティ識別子) 構造体。  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>コメント  
 アドレスを返します、`SID`構造体。  
  
##  <a name="sid"></a>  CSid::Sid  
 返します、`SID`を文字列として (セキュリティ識別子) 構造体。  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 返します、`SID`表示、ストレージ、または送信に適した形式の文字列として構造体。 等価[ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399)です。  
  
##  <a name="sidnameuse"></a>  CSid::SidNameUse  
 状態の説明を返します、`CSid`オブジェクト。  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 状態を示す値を格納するデータ メンバーの値を返します、`CSid`オブジェクト。  
  
|[値]|説明|  
|-----------|-----------------|  
|SidTypeUser|ユーザーを示す`SID`(セキュリティ識別子)。|  
|SidTypeGroup|グループを示す`SID`です。|  
|SidTypeDomain|ドメインを示す`SID`です。|  
|SidTypeAlias|別名を示す`SID`です。|  
|SidTypeWellKnownGroup|示します、`SID`のよく知られているグループ。|  
|SidTypeDeletedAccount|示します、`SID`削除されたアカウントにします。|  
|SidTypeInvalid|無効なことを示します`SID`です。|  
|SidTypeUnknown|不明なを示す`SID`型です。|  
|SidTypeComputer|示します、`SID`コンピューター用です。|  
  
### <a name="remarks"></a>コメント  
 呼び出す[CSid::LoadAccount](#loadaccount)を更新する、`CSid`呼び出す前にオブジェクト`SidNameUse`の状態に戻ります。 `SidNameUse` オブジェクトの状態は変更されません (を呼び出すことによって**LookupAccountName**または**LookupAccountSid**)、現在の状態のみが返されますが、します。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティのグローバル関数](../../atl/reference/security-global-functions.md)   
 [演算子](../../atl/reference/atl-operators.md)
