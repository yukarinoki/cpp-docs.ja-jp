---
title: IAccessorImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
ms.openlocfilehash: 6b9830ac2b6f1eacedd1b59184292f2148087093
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210864"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl クラス

[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T,
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
行セットまたはコマンドオブジェクトクラス。

*BindType*<br/>
バインド情報のストレージユニット。 既定値は `ATLBINDINGS` の構造です (「atldb.h」を参照してください)。

*BindingVector*<br/>
列情報の格納単位。 既定値は、キー要素が HACCESSOR 値、value 要素が `BindType` 構造体へのポインターである、 [CAtlMap](../../atl/reference/catlmap-class.md)です。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[IAccessorImpl](#iaccessorimpl)|コンストラクターです。|

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[AddRefAccessor](#addrefaccessor)|既存のアクセサーの参照カウントをインクリメントします。|
|[CreateAccessor](#createaccessor)|バインディングのセットからアクセサーを作成します。|
|[GetBindings](#getbindings)|アクセサーのバインディングを返します。|
|[ReleaseAccessor](#releaseaccessor)|アクセサーを解放します。|

## <a name="remarks"></a>解説

これは、行セットとコマンドに対して必須です。 OLE DB には、 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85))構造体の配列へのタグである haccessor を実装するプロバイダーが必要です。 `IAccessorImpl` によって提供される HACCESSORs は、`BindType` 構造体のアドレスです。 既定では、`BindType` は `IAccessorImpl`のテンプレート定義で `ATLBINDINGS` として定義されます。 `BindType` は、`IAccessorImpl` が `DBBINDING` 配列内の要素の数と参照カウントおよびアクセサーフラグを追跡するために使用する機構を提供します。

## <a name="iaccessorimpliaccessorimpl"></a><a name="iaccessorimpl"></a>IAccessorImpl:: IAccessorImpl

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
IAccessorImpl();
```

## <a name="iaccessorimpladdrefaccessor"></a><a name="addrefaccessor"></a>IAccessorImpl:: AddRefAccessor

既存のアクセサーの参照カウントをインクリメントします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IAccessor:: addrefaccessor](/previous-versions/windows/desktop/ms714978(v=vs.85)) 」を参照してください。

## <a name="iaccessorimplcreateaccessor"></a><a name="createaccessor"></a>IAccessorImpl:: CreateAccessor

バインディングのセットからアクセサーを作成します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,
   DBCOUNTITEM cBindings,
   const DBBINDING rgBindings[],
   DBLENGTH cbRowSize,
   HACCESSOR* phAccessor,
   DBBINDSTATUS rgStatus[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IAccessor:: createaccessor](/previous-versions/windows/desktop/ms720969(v=vs.85)) 」を参照してください。

## <a name="iaccessorimplgetbindings"></a><a name="getbindings"></a>IAccessorImpl:: GetBindings

アクセサーのコンシューマーからの基本的な列バインドを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,
   DBACCESSORFLAGS* pdwAccessorFlags,
   DBCOUNTITEM* pcBindings,
   DBBINDING** prgBindings);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IAccessor:: getbindings](/previous-versions/windows/desktop/ms721253(v=vs.85)) 」を参照してください。

## <a name="iaccessorimplreleaseaccessor"></a><a name="releaseaccessor"></a>IAccessorImpl:: ReleaseAccessor

アクセサーを解放します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IAccessor:: releaseaccessor](/previous-versions/windows/desktop/ms719717(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
