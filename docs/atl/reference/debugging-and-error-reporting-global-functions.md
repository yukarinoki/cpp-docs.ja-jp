---
title: グローバル関数のデバッグとエラー報告
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7636b1f4e13340b223edd8c63c39bbeb21c8bd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330203"
---
# <a name="debugging-and-error-reporting-global-functions"></a>グローバル関数のデバッグとエラー報告

これらの関数は、デバッグ機能とトレース機能を提供します。

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|HRESULT`GetLastError`の形式でエラー コードを返します。|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 エラー コードを HRESULT に変換します。|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|エラーの`IErrorInfo`詳細をクライアントに提供するように設定します。|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|`CAtlException` をスローします。|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。|

## <a name="atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>ラストエラーから取得します。

呼び出し側スレッドの直前のエラー コード値を HRESULT の形式で返します。

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>解説

`AtlHresultFromLastError`最後`GetLastError`のエラーを取得し、HRESULT_FROM_WIN32 マクロを使用して HRESULT に変換した後にエラーを返します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli.h

## <a name="atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>アトルフデレフロイン32

Win32 エラー コードを HRESULT に変換します。

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
変換するエラー値。

### <a name="remarks"></a>解説

マクロ HRESULT_FROM_WIN32を使用して、Win32 エラー コードを HRESULT に変換します。

> [!NOTE]
> を使用`HRESULT_FROM_WIN32(GetLastError())`する代わりに、関数を使用[します](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli.h

## <a name="atlreporterror"></a><a name="atlreporterror"></a>レポートエラー

オブジェクトのクライアント`IErrorInfo`にエラー情報を提供するようにインターフェイスを設定します。

```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
[in]エラーを報告するオブジェクトの CLSID。

*lpszDesc*<br/>
[in]エラーを説明する文字列。 ユニコード・バージョンは *、lpszDesc*がタイプ LPCOLESTR であることを指定します。ANSI バージョンは LPCSTR の種類を指定します。

*Iid*<br/>
[in]エラーを定義するインターフェイスの IID またはGUID_NULLエラーがオペレーティング システムによって定義されている場合。

*hRes*<br/>
[in]呼び出し元に返される HRESULT。

*nID*<br/>
[in]エラー記述文字列が格納されるリソース識別子。 この値は 0x0200 から 0xFFFF の間にあって、包括的に指定する必要があります。 デバッグ ビルドでは *、nID*が有効な文字列にインデックスを付けていない場合 **、ASSERT**が生成されます。 リリース ビルドでは、エラーの説明文字列が "不明なエラー" に設定されます。

*ヘルプID*<br/>
[in]エラーのヘルプ コンテキスト識別子。

*ファイル*<br/>
[in]エラーを説明するヘルプ ファイルのパスと名前。

*hInst*<br/>
[in]リソースへのハンドル。 既定では、このパラメーター`__AtlBaseModuleModule::GetResourceInstance``__AtlBaseModuleModule`は 、 [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)のグローバル インスタンス、またはそこから派生したクラスです。

### <a name="return-value"></a>戻り値

*hRes*パラメータが 0 以外の場合は *、hRes*の値を返します。 *hRes*がゼロの場合、戻り値の`AtlReportError`最初の 4 つのバージョンDISP_E_EXCEPTION。 最後の 2 つのバージョンは、マクロ**MAKE_HRESULT( 1, FACILITY_ITF,)** `nID` **の結果を返します**。

### <a name="remarks"></a>解説

文字列*lpszDesc*は、エラーのテキスト記述として使用されます。 クライアントは、戻り値`AtlReportError`の*hRes*を受け取ると、`IErrorInfo`エラーの詳細を得るための構造体にアクセスできます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
> C++`AtlReportError`のキャッチ ハンドラーでは使用しないでください。 これらの関数のオーバーライドの中には、内部で ATL 文字列変換マクロを`_alloca`使用するものもあります。 C++ の catch ハンドラーで使用`AtlReportError`すると、C++ の catch ハンドラーで例外が発生する可能性があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="atlthrow"></a><a name="atlthrow"></a>アトルスロー

HRESULT 状態コードに基づいてエラーを通知するには、この関数を呼び出します。

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>パラメーター

*人事*<br/>
標準 HRESULT 値。

### <a name="remarks"></a>解説

この関数は、エラー状態の場合に ATL コードと MFC コードで使用されます。 また、独自のコードから呼び出すこともできます。 この関数の既定の実装は、シンボル _ATL_NO_EXCEPTIONSの定義と、プロジェクトの種類 (MFC または ATL) によって異なります。

いずれの場合も、この関数は、デバッガーに HRESULT をトレースします。

Visual Studio 2015 更新プログラム 3 以降では、この関数は、偽の SAL 警告を回避するために__declspec (noreturn) に属性が設定されています。

_ATL_NO_EXCEPTIONSが MFC プロジェクトで定義されていない場合、この関数は、HRESULT の値に基づいて[CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)をスローします。

_ATL_NO_EXCEPTIONSが ATL プロジェクトで定義されていない場合、関数は[CAtlException](../../atl/reference/catlexception-class.md)をスローします。

_ATL_NO_EXCEPTIONS定義されている場合、関数は例外をスローする代わりにアサーション エラーを発生させます。

ATL プロジェクトでは、この関数を独自に実装して、障害が発生した場合に ATL が使用できるようにすることができます。 これを行うには、関数の名前と同じシグネチャ`AtlThrow`を持つ独自`AtlThrow`の関数を定義し、#defineします。 これは、atlexcept.h を含める前に行う必要があります (atlbase.h には atlexcept.h が含まれているため、ATL ヘッダーを含める前に行う必要があります)。 SAL`__declspec(noreturn)`警告を回避するために関数に属性を設定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>必要条件

**ヘッダー:** atldef.h

## <a name="atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>アトルスローラストウィン32

Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>解説

この関数は、デバッガーの結果`GetLastError`をトレースします。

_ATL_NO_EXCEPTIONSが MFC プロジェクトで定義されていない場合、この関数は、によって返される`GetLastError`値に基づいて[CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)をスローします。

_ATL_NO_EXCEPTIONSが ATL プロジェクトで定義されていない場合、関数は[CAtlException](../../atl/reference/catlexception-class.md)をスローします。

_ATL_NO_EXCEPTIONS定義されている場合、関数は例外をスローする代わりにアサーション エラーを発生させます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldef.h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[デバッグおよびエラー報告マクロ](../../atl/reference/debugging-and-error-reporting-macros.md)
