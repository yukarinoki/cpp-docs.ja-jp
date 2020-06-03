---
title: クラス
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
ms.openlocfilehash: 2fcfdfecab649b571047613ec0889b02d2c7a7a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331413"
---
# <a name="cprivateobjectsecuritydesc-class"></a>クラス

このクラスは、プライベート オブジェクトのセキュリティ記述子オブジェクトを表します。

## <a name="syntax"></a>構文

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[セキュリティサービス::Cプライベートオブジェクトセキュリティデス](#cprivateobjectsecuritydesc)|コンストラクターです。|
|[セキュリティサービス::~Cプライベートオブジェクトセキュリティデス](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を継承します。](#converttoautoinherit)|セキュリティ記述子とそのアクセス制御リスト (ACL) を、継承可能なアクセス制御エントリ (ACE) の自動伝達をサポートする形式に変換します。|
|[Cプライベートオブジェクトセキュリティデスク::作成](#create)|呼び出し元のリソース マネージャーによって作成されたプライベート オブジェクトの自己相対セキュリティ記述子を割り当て、初期化します。|
|[セキュリティサービス::取得](#get)|プライベート オブジェクトのセキュリティ記述子から情報を取得します。|
|[セキュリティサービス::セット](#set)|プライベート オブジェクトのセキュリティ記述子を変更します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

このクラスは[、CSecurityDesc](../../atl/reference/csecuritydesc-class.md)から派生したプライベート オブジェクトのセキュリティ記述子を作成および管理するためのメソッドを提供します。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[セキュリティデス](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a>を継承します。

セキュリティ記述子とそのアクセス制御リスト (ACL) を、継承可能なアクセス制御エントリ (ACE) の自動伝達をサポートする形式に変換します。

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>パラメーター

*親*<br/>
オブジェクトの親コンテナを参照する[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクトへのポインター。 親コンテナがない場合、このパラメータは NULL です。

*オブジェクトタイプ*<br/>
現在の`GUID`オブジェクトに関連付けられているオブジェクトの型を識別する構造体へのポインター。 オブジェクトに GUID がない場合は *、ObjectType*を NULL に設定します。

*オブジェクト*<br/>
新しいオブジェクトに他のオブジェクトを含めることができるかどうかを指定します。 値が true の場合、新しいオブジェクトがコンテナーであることを示します。 値が false の場合、新しいオブジェクトがコンテナーではないことを示します。

*ジェネリックマッピング*<br/>
オブジェクトに対する各ジェネリック権限から特定の権限へのマッピングを指定する[GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

このメソッドは、現在のセキュリティ記述子の随意アクセス制御リスト (DACL) およびシステム アクセス制御リスト (SACL) 内の ACE が親セキュリティ記述子から継承されたかどうかを判断しようとします。 関数[を](/windows/win32/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity)呼び出します。

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a>セキュリティサービス::Cプライベートオブジェクトセキュリティデス

コンストラクターです。

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>解説

`CPrivateObjectSecurityDesc` オブジェクトを初期化します。

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a>セキュリティサービス::~Cプライベートオブジェクトセキュリティデス

デストラクターです。

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>解説

デストラクターは、割り当てられたすべてのリソースを解放し、プライベート オブジェクトのセキュリティ記述子を削除します。

## <a name="cprivateobjectsecuritydesccreate"></a><a name="create"></a>Cプライベートオブジェクトセキュリティデスク::作成

呼び出し元のリソース マネージャーによって作成されたプライベート オブジェクトの自己相対セキュリティ記述子を割り当て、初期化します。

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

*親*<br/>
新しいオブジェクトが作成される親ディレクトリを参照する[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクトへのポインター。 親ディレクトリがない場合は NULL に設定します。

*pクリエーター*<br/>
オブジェクトの作成者によって提供されるセキュリティ記述子へのポインター。 オブジェクトの作成者が新しいオブジェクトのセキュリティ情報を明示的に渡さない場合は、このパラメーターを NULL に設定します。

*オブジェクト*<br/>
新しいオブジェクトに他のオブジェクトを含めることができるかどうかを指定します。 値が true の場合、新しいオブジェクトがコンテナーであることを示します。 値が false の場合、新しいオブジェクトがコンテナーではないことを示します。

*トークン*<br/>
オブジェクトを作成するクライアント プロセスの[CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトへの参照。

*ジェネリックマッピング*<br/>
オブジェクトに対する各ジェネリック権限から特定の権限へのマッピングを指定する[GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping)構造体へのポインター。

*オブジェクトタイプ*<br/>
現在の`GUID`オブジェクトに関連付けられているオブジェクトの型を識別する構造体へのポインター。 オブジェクトに GUID がない場合は *、ObjectType*を NULL に設定します。

*オブジェクト*<br/>
新しいオブジェクトに他のオブジェクトを含めることができるかどうかを指定します。 値が true の場合、新しいオブジェクトがコンテナーであることを示します。 値が false の場合、新しいオブジェクトがコンテナーではないことを示します。

*フラグを自動継承*<br/>
アクセス制御エントリ (ACE) が*pParent*から継承される方法を制御するビット フラグのセット。 詳細については[、「プライベートオブジェクトセキュリティExの作成](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)」を参照してください。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

このメソッド[は、プライベート オブジェクトのセルキュリティ](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity)またはを呼び出[します](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)。

2 番目のメソッドでは、新しいオブジェクトのオブジェクト型 GUID を指定したり、ACE の継承方法を制御したりできます。

> [!NOTE]
> 自己相対セキュリティ記述子は、すべてのセキュリティ情報を連続したメモリ ブロックに格納するセキュリティ記述子です。

## <a name="cprivateobjectsecuritydescget"></a><a name="get"></a>セキュリティサービス::取得

プライベート オブジェクトのセキュリティ記述子から情報を取得します。

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>パラメーター

*Si*<br/>
取得するセキュリティ記述子の部分を示すビット フラグのセット。 この値は[、SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information)ビット フラグの組み合わせになります。

*結果*<br/>
指定されたセキュリティ記述子から要求された情報のコピーを受け取る[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

セキュリティ記述子は、セキュリティ保護可能なオブジェクトのセキュリティ情報を含む構造体と関連データです。

## <a name="cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a>を指定します。

代入演算子。

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
現在のオブジェクトに代入する `CPrivateObjectSecurityDesc` オブジェクト。

### <a name="return-value"></a>戻り値

更新された`CPrivateObjectSecurityDesc`オブジェクトを返します。

## <a name="cprivateobjectsecuritydescset"></a><a name="set"></a>セキュリティサービス::セット

プライベート オブジェクトのセキュリティ記述子を変更します。

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

*Si*<br/>
設定するセキュリティ記述子の部分を示すビット フラグのセット。 この値は[、SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information)ビット フラグの組み合わせになります。

*変更*<br/>
[オブジェクト](../../atl/reference/csecuritydesc-class.md)へのポインター。 *si*パラメータで示されるこのセキュリティ記述子の部分は、オブジェクトのセキュリティ記述子に適用されます。

*ジェネリックマッピング*<br/>
オブジェクトに対する各ジェネリック権限から特定の権限へのマッピングを指定する[GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping)構造体へのポインター。

*トークン*<br/>
オブジェクトを作成するクライアント プロセスの[CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトへの参照。

*フラグを自動継承*<br/>
アクセス制御エントリ (ACE) が*pParent*から継承される方法を制御するビット フラグのセット。 詳細については[、「プライベートオブジェクトセキュリティExの作成](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)」を参照してください。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

2 番目のメソッドでは、オブジェクトのオブジェクト型 GUID を指定したり、ACE の継承方法を制御したりできます。

## <a name="see-also"></a>関連項目

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)<br/>
[クラスをセキュリティします。](../../atl/reference/csecuritydesc-class.md)
