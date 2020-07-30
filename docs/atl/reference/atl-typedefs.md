---
title: ATL Typedefs
ms.date: 11/04/2016
f1_keywords:
- atlcore/ATL::_ATL_BASE_MODULE
- atlbase/ATL::_ATL_COM_MODULE
- atlbase/ATL::_ATL_MODULE
- atlbase/ATL::_ATL_WIN_MODULE
- atlutil/ATL::ATL_URL_PORT
- atlbase/ATL::CComDispatchDriver
- atlbase/ATL::CComGlobalsThreadModel
- atlbase/ATL::CComObjectThreadModel
- atlwin/ATL::CContainedWindow
- atlpath/ATL::CPath
- atlpath/ATL::CPathA
- atlpath/ATL::CPathW
- " atlsimpcoll/ATL::CSimpleValArray"
- " atlutil/ATL::LPCURL"
- atlbase/ATL::DefaultThreadTraits
- atlutil/ATL::LPURL
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
ms.openlocfilehash: a6b1ce33fe201338a0cc9356f2ef86e598629fd6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228038"
---
# <a name="atl-typedefs"></a>ATL Typedefs

Active Template Library には、次の typedef が含まれています。

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)に基づく typedef として定義されます。|
|[_ATL_COM_MODULE](#_atl_com_module)|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)に基づく typedef として定義されます。|
|[_ATL_MODULE](#_atl_module)|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)に基づく typedef として定義されます。|
|[_ATL_WIN_MODULE](#_atl_win_module)|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)に基づく typedef として定義されます。|
|[ATL_URL_PORT](#atl_url_port)|ポート番号を指定するために[CUrl](../../atl/reference/curl-class.md)によって使用される型。|
|[CComDispatchDriver](#ccomdispatchdriver)|このクラスは、COM インターフェイスポインターを管理します。|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|使用されているスレッドモデルに関係なく、適切なスレッドモデルメソッドを呼び出します。|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|使用されているスレッドモデルに関係なく、適切なスレッドモデルメソッドを呼び出します。|
|[CContainedWindow](#ccontainedwindow)|このクラスは、の特殊化です `CContainedWindowT` 。|
|[CPath](#cpath)|を使用した[Cpatht](../../atl/reference/cpatht-class.md)の特殊化 `CString` 。|
|[CPathA](#cpatha)|を使用した[Cpatht](../../atl/reference/cpatht-class.md)の特殊化 `CStringA` 。|
|[CPathW](#cpathw)|を使用した[Cpatht](../../atl/reference/cpatht-class.md)の特殊化 `CStringW` 。|
|[CSimpleValArray](#csimplevalarray)|単純型を格納するための配列を表します。|
|[DefaultThreadTraits](#defaultthreadtraits)|既定のスレッド特徴クラス。|
|[LPCURL](#lpcurl)|定数[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインター。|
|[LPURL](#lpurl)|[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインターです。|

## <a name="_atl_base_module"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE

_ATL_BASE_MODULE70 に基づく typedef として定義されます。

```cpp
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>解説

すべての ATL プロジェクトで使用されます。 [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)に基づいています。

ATL 7.0 モジュールクラスの一部であるクラスは、_ATL_BASE_MODULE 構造体から派生します。  ATL モジュールクラスの詳細については、「 [COM Modules クラス](../../atl/com-modules-classes.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlcore .h

## <a name="_atl_com_module"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE

_ATL_COM_MODULE70 に基づく typedef として定義されます。

```cpp
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>解説

COM 機能を使用する ATL プロジェクトによって使用されます。 [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)に基づいています。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="_atl_module"></a><a name="_atl_module"></a>_ATL_MODULE

_ATL_MODULE70 に基づく typedef として定義されます。

```cpp
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

### <a name="requirements"></a>必要条件

**項目**

### <a name="remarks"></a>解説

[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)に基づいています。

## <a name="_atl_win_module"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE

_ATL_WIN_MODULE70 に基づく typedef として定義されます。

```cpp
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>解説

ウィンドウ機能を使用する ATL プロジェクトによって使用されます。 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)に基づいています。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="atl_url_port"></a><a name="atl_url_port"></a>ATL_URL_PORT

ポート番号を指定するために[CUrl](curl-class.md)によって使用される型。

```cpp
typedef WORD ATL_URL_PORT;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlutil. h

## <a name="ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CComDispatchDriver

このクラスは、COM インターフェイスポインターを管理します。

```cpp
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel

使用されているスレッドモデルに関係なく、適切なスレッドモデルメソッドを呼び出します。

```cpp
#if defined(_ATL_SINGLE_THREADED)
typedef CComSingleThreadModel CComGlobalsThreadModel;
#elif defined(_ATL_APARTMENT_THREADED)
typedef CComMultiThreadModel CComGlobalsThreadModel;
#elif defined(_ATL_FREE_THREADED)
typedef CComMultiThreadModel CComGlobalsThreadModel;
#else
#pragma message ("No global threading model defined")
#endif
```

### <a name="remarks"></a>解説

アプリケーションで使用されるスレッドモデルに応じて、 **`typedef`** 名前は `CComGlobalsThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)のいずれかを参照します。 これらのクラス **`typedef`** は、重要なセクションクラスを参照するための追加の名前を提供します。

> [!NOTE]
> `CComGlobalsThreadModel`はクラス[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)を参照していません。

を使用 `CComGlobalsThreadModel` すると、特定のスレッドモデルクラスを指定できます。 使用されているスレッドモデルに関係なく、適切なメソッドが呼び出されます。

に加え `CComGlobalsThreadModel` て、ATL には CComObjectThreadModel という名前が付いて **`typedef`** います。 [CComObjectThreadModel](#ccomobjectthreadmodel) によって参照されるクラスは、 **`typedef`** 次の表に示すように、使用されるスレッドモデルによって異なります。

|Typedef|単一スレッド|アパートメントスレッド|フリースレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ;M =`CComMultiThreadModel`

`CComObjectThreadModel`単一のオブジェクトクラス内で使用します。 `CComGlobalsThreadModel`プログラムでグローバルに使用できるオブジェクトでを使用するか、複数のスレッド間でモジュールリソースを保護する必要がある場合は、を使用します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>CComObjectThreadModel

使用されているスレッドモデルに関係なく、適切なスレッドモデルメソッドを呼び出します。

```cpp
#if defined(_ATL_SINGLE_THREADED)
typedef CComSingleThreadModel CComObjectThreadModel;
#elif defined(_ATL_APARTMENT_THREADED)
typedef CComSingleThreadModel CComObjectThreadModel;
#elif defined(_ATL_FREE_THREADED)
typedef CComMultiThreadModel CComObjectThreadModel;
#else
#pragma message ("No global threading model defined")
#endif
```

### <a name="remarks"></a>解説

アプリケーションで使用されるスレッドモデルに応じて、 **`typedef`** 名前は `CComObjectThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)のいずれかを参照します。 これらのクラス **`typedef`** は、重要なセクションクラスを参照するための追加の名前を提供します。

> [!NOTE]
> `CComObjectThreadModel`はクラス[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)を参照していません。

を使用 `CComObjectThreadModel` すると、特定のスレッドモデルクラスを指定できます。 使用されているスレッドモデルに関係なく、適切なメソッドが呼び出されます。

に加え `CComObjectThreadModel` て、ATL には CComGlobalsThreadModel という名前が付いて **`typedef`** います。 [CComGlobalsThreadModel](#ccomglobalsthreadmodel) によって参照されるクラスは、 **`typedef`** 次の表に示すように、使用されるスレッドモデルによって異なります。

|Typedef|単一スレッド|アパートメントスレッド|フリースレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ;M =`CComMultiThreadModel`

`CComObjectThreadModel`単一のオブジェクトクラス内で使用します。 `CComGlobalsThreadModel`プログラムでグローバルに使用できるオブジェクトでを使用するか、複数のスレッド間でモジュールリソースを保護する必要がある場合は、を使用します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="ccontainedwindow"></a><a name="ccontainedwindow"></a>CContainedWindow

このクラスは、の特殊化です `CContainedWindowT` 。

```cpp
typedef CContainedWindowT<CWindow> CContainedWindow;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

### <a name="remarks"></a>解説

`CContainedWindow`は[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の特殊化です。 基底クラスまたは特徴を変更する場合は、を `CContainedWindowT` 直接使用します。

## <a name="cpath"></a><a name="cpath"></a>CPath

を使用した[Cpatht](../../atl/reference/cpatht-class.md)の特殊化 `CString` 。

```cpp
typedef CPathT<CString> CPath;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlpath .h

## <a name="cpatha"></a><a name="cpatha"></a>CPathA

を使用した[Cpatht](../../atl/reference/cpatht-class.md)の特殊化 `CStringA` 。

```cpp
typedef CPathT<CStringA> CPathA;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlpath .h

## <a name="cpathw"></a><a name="cpathw"></a>CPathW

を使用した[Cpatht](../../atl/reference/cpatht-class.md)の特殊化 `CStringW` 。

```cpp
typedef ATL::CPathT<CStringW> CPathW;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlpath .h

## <a name="csimplevalarray"></a><a name="csimplevalarray"></a>CSimpleValArray

単純型を格納するための配列を表します。

```cpp
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>解説

`CSimpleValArray`は、単純なデータ型を含む配列を作成および管理するために用意されています。 [CSimpleArray](../../atl/reference/csimplearray-class.md)の単純な #define です。

### <a name="requirements"></a>必要条件

**ヘッダー:** atl. h

## <a name="lpcurl"></a><a name="lpcurl"></a>LPCURL

定数[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインター。

```cpp
typedef const CUrl* LPCURL;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlutil. h

## <a name="defaultthreadtraits"></a><a name="defaultthreadtraits"></a>DefaultThreadTraits

既定のスレッド特徴クラス。

### <a name="syntax"></a>構文

```cpp
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>解説

現在のプロジェクトがマルチスレッド CRT を使用している場合、DefaultThreadTraits は CRTThreadTraits として定義されます。 それ以外の場合は、Win32ThreadTraits が使用されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="lpurl"></a><a name="lpurl"></a>LPURL

[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインターです。

```cpp
typedef CUrl* LPURL;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlutil. h

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)<br/>
[関数](../../atl/reference/atl-functions.md)<br/>
[グローバル変数](../../atl/reference/atl-global-variables.md)<br/>
[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[[マクロ]](../../atl/reference/atl-macros.md)
