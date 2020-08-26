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
ms.openlocfilehash: 356278b316912bdb81f1c43bbf2034f00ec3d785
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845615"
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
バインド情報のストレージユニット。 既定値は `ATLBINDINGS` 構造体です (「atldb.h」を参照してください)。

*BindingVector*<br/>
列情報の格納単位。 既定 [では、](../../atl/reference/catlmap-class.md) キー要素は haccessor 値、value 要素は構造体へのポインターです `BindType` 。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[IAccessorImpl](#iaccessorimpl)|コンストラクターです。|

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[AddRefAccessor](#addrefaccessor)|既存のアクセサーの参照カウントをインクリメントします。|
|[CreateAccessor](#createaccessor)|バインディングのセットからアクセサーを作成します。|
|[GetBindings](#getbindings)|アクセサーのバインディングを返します。|
|[ReleaseAccessor](#releaseaccessor)|アクセサーを解放します。|

## <a name="remarks"></a>解説

これは、行セットとコマンドに対して必須です。 OLE DB には、 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 構造体の配列へのタグである haccessor を実装するプロバイダーが必要です。 によって提供される HACCESSORs `IAccessorImpl` は、構造体のアドレスです `BindType` 。 既定で `BindType` は、はのテンプレート定義のとして定義されてい `ATLBINDINGS` `IAccessorImpl` ます。 `BindType``IAccessorImpl`配列内の要素の数 `DBBINDING` だけでなく、参照カウントとアクセサーフラグも追跡するためにによって使用される機構を提供します。

## <a name="iaccessorimpliaccessorimpl"></a><a name="iaccessorimpl"></a> IAccessorImpl:: IAccessorImpl

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
IAccessorImpl();
```

## <a name="iaccessorimpladdrefaccessor"></a><a name="addrefaccessor"></a> IAccessorImpl:: AddRefAccessor

既存のアクセサーの参照カウントをインクリメントします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IAccessor:: addrefaccessor](/previous-versions/windows/desktop/ms714978(v=vs.85)) 」を参照してください。

## <a name="iaccessorimplcreateaccessor"></a><a name="createaccessor"></a> IAccessorImpl:: CreateAccessor

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

## <a name="iaccessorimplgetbindings"></a><a name="getbindings"></a> IAccessorImpl:: GetBindings

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

## <a name="iaccessorimplreleaseaccessor"></a><a name="releaseaccessor"></a> IAccessorImpl:: ReleaseAccessor

アクセサーを解放します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IAccessor:: releaseaccessor](/previous-versions/windows/desktop/ms719717(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
