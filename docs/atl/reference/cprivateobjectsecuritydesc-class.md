---
title: CPrivateObjectSecurityDesc クラス
ms.date: 11/04/2016
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
ms.openlocfilehash: cc726892515ea38a559bdf182affa96f84be3449
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503300"
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc クラス

このクラスは、プライベート オブジェクトのセキュリティ記述子オブジェクトを表します。

## <a name="syntax"></a>構文

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|コンストラクターです。|
|[CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|セキュリティ記述子とそのアクセス制御リスト (Acl) を継承可能なアクセス制御エントリ (Ace) の自動適用をサポートする形式に変換するには、このメソッドを呼び出します。|
|[CPrivateObjectSecurityDesc::Create](#create)|割り当て、呼び出し元のリソース マネージャーによって作成されたプライベート オブジェクト用の自己相対のセキュリティ記述子を初期化するには、このメソッドを呼び出します。|
|[CPrivateObjectSecurityDesc::Get](#get)|プライベート オブジェクトのセキュリティ記述子から情報を取得するには、このメソッドを呼び出します。|
|[CPrivateObjectSecurityDesc::Set](#set)|プライベート オブジェクトのセキュリティ記述子を変更するには、このメソッドを呼び出します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[operator=](#operator_eq)|代入演算子。|

## <a name="remarks"></a>Remarks

このクラスから派生した[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)メソッドの作成と、プライベート オブジェクトのセキュリティ記述子の管理を提供します。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

##  <a name="converttoautoinherit"></a>  CPrivateObjectSecurityDesc::ConvertToAutoInherit

セキュリティ記述子とそのアクセス制御リスト (Acl) を継承可能なアクセス制御エントリ (Ace) の自動適用をサポートする形式に変換するには、このメソッドを呼び出します。

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
ポインターを[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクトの親コンテナーを参照するオブジェクト。 親コンテナーがない場合は、このパラメーターは NULL です。

*ObjectType*<br/>
ポインター、`GUID`現在のオブジェクトに関連付けられているオブジェクトの種類を識別する構造体。 設定*ObjectType*オブジェクトは、GUID を持っていない場合は NULL にします。

*bIsDirectoryObject*<br/>
新しいオブジェクトが他のオブジェクトを含めるかどうかを指定します。 値が true は、新しいオブジェクトがコンテナーであることを示します。 False の値は、新しいオブジェクトがコンテナーではないことを示します。

*GenericMapping*<br/>
ポインターを[GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping)オブジェクトの特定の権限を各ジェネリック右からマッピングを指定する構造体。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>Remarks

このメソッドは随意アクセス制御の Ace が (DACL) を一覧表示するかどうかを決定しようと現在のセキュリティ記述子のシステム アクセス制御リスト (SACL) は、親のセキュリティ記述子から継承されました。 呼び出す、 [ConvertToAutoInheritPrivateObjectSecurity](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity)関数。

##  <a name="cprivateobjectsecuritydesc"></a>  CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc

コンストラクターです。

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Remarks

`CPrivateObjectSecurityDesc` オブジェクトを初期化します。

##  <a name="dtor"></a>  CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc

デストラクターです。

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Remarks

デストラクターは、割り当てられているすべてのリソースを解放し、プライベート オブジェクトのセキュリティ記述子を削除します。

##  <a name="create"></a>  CPrivateObjectSecurityDesc::Create

割り当て、呼び出し元のリソース マネージャーによって作成されたプライベート オブジェクト用の自己相対のセキュリティ記述子を初期化するには、このメソッドを呼び出します。

```
bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
ポインターを[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)新しいオブジェクトを作成する親ディレクトリを参照するオブジェクト。 親ディレクトリが存在しない場合は NULL に設定します。

*pCreator*<br/>
オブジェクトの作成者によって提供されるセキュリティ記述子へのポインター。 オブジェクトの作成者が明示的に新しいオブジェクトのセキュリティ情報を渡さない場合は、このパラメーターを NULL に設定します。

*bIsDirectoryObject*<br/>
新しいオブジェクトが他のオブジェクトを含めるかどうかを指定します。 値が true は、新しいオブジェクトがコンテナーであることを示します。 False の値は、新しいオブジェクトがコンテナーではないことを示します。

*トークン*<br/>
参照、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトが作成されている対象のクライアント プロセスのオブジェクト。

*GenericMapping*<br/>
ポインターを[GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping)オブジェクトの特定の権限を各ジェネリック右からマッピングを指定する構造体。

*ObjectType*<br/>
ポインター、`GUID`現在のオブジェクトに関連付けられているオブジェクトの種類を識別する構造体。 設定*ObjectType*オブジェクトは、GUID を持っていない場合は NULL にします。

*bIsContainerObject*<br/>
新しいオブジェクトが他のオブジェクトを含めるかどうかを指定します。 値が true は、新しいオブジェクトがコンテナーであることを示します。 False の値は、新しいオブジェクトがコンテナーではないことを示します。

*AutoInheritFlags*<br/>
アクセス制御エントリ (Ace) の継承方法を制御するビット フラグのセット*pParent*します。 参照してください[CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)の詳細。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出す[CreatePrivateObjectSercurity](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity)または[CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)します。

2 番目のメソッドは、新しいオブジェクトのオブジェクトの種類の GUID を指定するか、Ace が継承される方法を制御するを許可します。

> [!NOTE]
>  自己相対セキュリティ記述子は、連続するメモリ ブロックにすべてのセキュリティ情報を格納するセキュリティ記述子です。

##  <a name="get"></a>  CPrivateObjectSecurityDesc::Get

プライベート オブジェクトのセキュリティ記述子から情報を取得するには、このメソッドを呼び出します。

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>パラメーター

*si*<br/>
取得するセキュリティ記述子の部分を指定するビット フラグのセット。 この値の組み合わせを指定できます、 [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information)ビット フラグです。

*pResult*<br/>
ポインターを[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)を指定したセキュリティ記述子から要求された情報のコピーを受け取るオブジェクト。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>Remarks

セキュリティ記述子には、構造と関連データがセキュリティ保護可能なオブジェクトのセキュリティ情報が含まれています。

##  <a name="operator_eq"></a>  CPrivateObjectSecurityDesc::operator =

代入演算子。

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CPrivateObjectSecurityDesc`を現在のオブジェクトに割り当てるオブジェクト。

### <a name="return-value"></a>戻り値

更新された返します`CPrivateObjectSecurityDesc`オブジェクト。

##  <a name="set"></a>  CPrivateObjectSecurityDesc::Set

プライベート オブジェクトのセキュリティ記述子を変更するには、このメソッドを呼び出します。

```
bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```

### <a name="parameters"></a>パラメーター

*si*<br/>
設定するセキュリティ記述子の部分を指定するビット フラグのセット。 この値の組み合わせを指定できます、 [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information)ビット フラグです。

*変更*<br/>
ポインターを[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクト。 このセキュリティ記述子の部分が示される、 *si*パラメーターは、オブジェクトのセキュリティ記述子に適用されます。

*GenericMapping*<br/>
ポインターを[GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping)オブジェクトの特定の権限を各ジェネリック右からマッピングを指定する構造体。

*トークン*<br/>
参照、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトが作成されている対象のクライアント プロセスのオブジェクト。

*AutoInheritFlags*<br/>
アクセス制御エントリ (Ace) の継承方法を制御するビット フラグのセット*pParent*します。 参照してください[CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)の詳細。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>Remarks

2 番目のメソッドは、オブジェクトのオブジェクトの種類の GUID を指定することや、Ace の継承方法の制御を許可します。

## <a name="see-also"></a>関連項目

[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)<br/>
[CSecurityDesc クラス](../../atl/reference/csecuritydesc-class.md)
