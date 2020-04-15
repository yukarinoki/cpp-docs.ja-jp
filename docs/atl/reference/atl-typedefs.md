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
ms.openlocfilehash: 5548bee36ac52dbd6add31241714b0404289be45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319190"
---
# <a name="atl-typedefs"></a>ATL Typedefs

アクティブテンプレートライブラリには、次のタイプ定義が含まれています。

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)に基づいて型定義として定義されます。|
|[_ATL_COM_MODULE](#_atl_com_module)|_ATL_COM_MODULE70に基づいて型定義として定義[されます](../../atl/reference/atl-com-module70-structure.md)。|
|[_ATL_MODULE](#_atl_module)|_ATL_MODULE70に基づいて型定義として定義[されます](../../atl/reference/atl-module70-structure.md)。|
|[_ATL_WIN_MODULE](#_atl_win_module)|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)に基づく型定義として定義|
|[ATL_URL_PORT](#atl_url_port)|ポート番号を指定するために[CUrl](../../atl/reference/curl-class.md)によって使用される型。|
|[ドライバーを呼び出します。](#ccomdispatchdriver)|このクラスは、COM インターフェイス ポインタを管理します。|
|[スレッドモデル](#ccomglobalsthreadmodel)|使用されているスレッド モデルに関係なく、適切なスレッド モデル メソッドを呼び出します。|
|[オブジェクトスレッドモデル](#ccomobjectthreadmodel)|使用されているスレッド モデルに関係なく、適切なスレッド モデル メソッドを呼び出します。|
|[ウィンドウ](#ccontainedwindow)|このクラスは、 の専門`CContainedWindowT`クラスです。|
|[CPath](#cpath)|を使用した`CString` [CPathT](../../atl/reference/cpatht-class.md)の特殊化。|
|[CPathA](#cpatha)|を使用した`CStringA` [CPathT](../../atl/reference/cpatht-class.md)の特殊化。|
|[CPathW](#cpathw)|を使用した`CStringW` [CPathT](../../atl/reference/cpatht-class.md)の特殊化。|
|[アレイ](#csimplevalarray)|単純型を格納するための配列を表します。|
|[既定のスレッドトレイト](#defaultthreadtraits)|既定のスレッドの特徴クラス。|
|[LPカール](#lpcurl)|定数[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインター。|
|[LPURL](#lpurl)|[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインター。|

## <a name="_atl_base_module"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE

_ATL_BASE_MODULE70に基づいて型定義として定義されます。

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>解説

すべての ATL プロジェクトで使用されます。 [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)に基づく .

ATL 7.0 モジュール クラスの一部であるクラスは、_ATL_BASE_MODULE構造から派生します。  ATL モジュール クラスの詳細については[、COM モジュール クラス](../../atl/com-modules-classes.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="_atl_com_module"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE

_ATL_COM_MODULE70に基づいて型定義として定義されます。

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>解説

COM 機能を使用する ATL プロジェクトで使用されます。 [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)に基づく .

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="_atl_module"></a><a name="_atl_module"></a>_ATL_MODULE

_ATL_MODULE70に基づいて型定義として定義されます。

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>必要条件

**ヘッダー：**

### <a name="remarks"></a>解説

[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)に基づく .

## <a name="_atl_win_module"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE

_ATL_WIN_MODULE70に基づいて型定義として定義されます。

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>解説

ウィンドウ機能を使用する ATL プロジェクトで使用されます。 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)に基づく .

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atl_url_port"></a><a name="atl_url_port"></a>ATL_URL_PORT

ポート番号を指定するために[CUrl](curl-class.md)によって使用される型。

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>ドライバーを呼び出します。

このクラスは、COM インターフェイス ポインタを管理します。

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>スレッドモデル

使用されているスレッド モデルに関係なく、適切なスレッド モデル メソッドを呼び出します。

```
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

アプリケーションで使用されるスレッド モデルに応じて、**型定義**名`CComGlobalsThreadModel`は[CComSingleThreadModel または CComMultiThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)のいずれかを参照[します](../../atl/reference/ccommultithreadmodel-class.md)。 これらのクラスは、`typedef`クリティカル セクション クラスを参照するための追加の名前を提供します。

> [!NOTE]
> `CComGlobalsThreadModel`クラス[を](../../atl/reference/ccommultithreadmodelnocs-class.md)参照していません。

使用`CComGlobalsThreadModel`すると、特定のスレッド モデル クラスを指定できなくなります。 使用されているスレッド モデルに関係なく、適切なメソッドが呼び出されます。

に加えて`CComGlobalsThreadModel`、ATL は**型定義**名[を提供](#ccomobjectthreadmodel)します。 各`typedef`クラスが参照するクラスは、次の表に示すように、使用されるスレッド モデルによって異なります。

|Typedef|シングル スレッド|アパートメントスレッド|フリー スレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`;M=`CComMultiThreadModel`

単`CComObjectThreadModel`一のオブジェクト クラス内で使用します。 プログラム`CComGlobalsThreadModel`でグローバルに使用できるオブジェクト、または複数のスレッドにわたってモジュールリソースを保護する場合に使用します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>オブジェクトスレッドモデル

使用されているスレッド モデルに関係なく、適切なスレッド モデル メソッドを呼び出します。

```
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

アプリケーションで使用されるスレッド モデルに応じて、名前`typedef``CComObjectThreadModel`は[CCom シングル スレッド モデルまたは CComMultiThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)のいずれかを参照[します](../../atl/reference/ccommultithreadmodel-class.md)。 これらのクラスは、`typedef`クリティカル セクション クラスを参照するための追加の名前を提供します。

> [!NOTE]
> `CComObjectThreadModel`クラス[を](../../atl/reference/ccommultithreadmodelnocs-class.md)参照していません。

使用`CComObjectThreadModel`すると、特定のスレッド モデル クラスを指定できなくなります。 使用されているスレッド モデルに関係なく、適切なメソッドが呼び出されます。

に加えて`CComObjectThreadModel`、ATL は**型定義**名[CCom グローバルスレッドモデルを](#ccomglobalsthreadmodel)提供します。 各**typedef**によって参照されるクラスは、次の表に示すように、使用されるスレッド モデルによって異なります。

|Typedef|シングル スレッド|アパートメントスレッド|フリー スレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`;M=`CComMultiThreadModel`

単`CComObjectThreadModel`一のオブジェクト クラス内で使用します。 プログラム`CComGlobalsThreadModel`でグローバルに使用できるオブジェクト、または複数のスレッドにわたってモジュールリソースを保護する場合に使用します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccontainedwindow"></a><a name="ccontainedwindow"></a>ウィンドウ

このクラスは、 の専門`CContainedWindowT`クラスです。

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

### <a name="remarks"></a>解説

`CContainedWindow`は[CContained ウィンドウT](../../atl/reference/ccontainedwindowt-class.md)の特殊化です。 基本クラスまたは特性を変更する場合は、直接使用`CContainedWindowT`します。

## <a name="cpath"></a><a name="cpath"></a>CPath

を使用した`CString` [CPathT](../../atl/reference/cpatht-class.md)の特殊化。

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

## <a name="cpatha"></a><a name="cpatha"></a>CPathA

を使用した`CStringA` [CPathT](../../atl/reference/cpatht-class.md)の特殊化。

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

## <a name="cpathw"></a><a name="cpathw"></a>CPathW

を使用した`CStringW` [CPathT](../../atl/reference/cpatht-class.md)の特殊化。

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

## <a name="csimplevalarray"></a><a name="csimplevalarray"></a>アレイ

単純型を格納するための配列を表します。

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>解説

`CSimpleValArray`は、単純なデータ型を含む配列を作成および管理するために提供されています。 これは[、CSimpleArray](../../atl/reference/csimplearray-class.md)の単純な#defineです。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="lpcurl"></a><a name="lpcurl"></a>LPカール

定数[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインター。

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="defaultthreadtraits"></a><a name="defaultthreadtraits"></a>既定のスレッドトレイト

既定のスレッドの特徴クラス。

### <a name="syntax"></a>構文

```
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>解説

現在のプロジェクトがマルチスレッド CRT を使用している場合、既定のスレッドトレイトは CRTThreadTraits として定義されます。 それ以外の場合は、Win32ThreadTraits が使用されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="lpurl"></a><a name="lpurl"></a>LPURL

[CUrl](../../atl/reference/curl-class.md)オブジェクトへのポインター。

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)<br/>
[関数](../../atl/reference/atl-functions.md)<br/>
[グローバル変数](../../atl/reference/atl-global-variables.md)<br/>
[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[マクロ](../../atl/reference/atl-macros.md)
