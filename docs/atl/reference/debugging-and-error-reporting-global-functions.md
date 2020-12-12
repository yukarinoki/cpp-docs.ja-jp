---
description: 詳細については、「デバッグおよびエラー報告のグローバル関数」を参照してください。
title: デバッグとエラー報告のグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: 3c729a7d8e870ce7b104ca53cd83bf8c41112dea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139985"
---
# <a name="debugging-and-error-reporting-global-functions"></a>デバッグとエラー報告のグローバル関数

これらの関数は、便利なデバッグ機能とトレース機能を提供します。

|名前|説明|
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|`GetLastError`HRESULT の形式でエラーコードを返します。|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 エラー コードを HRESULT に変換します。|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|`IErrorInfo`クライアントにエラーの詳細を提供するように設定します。|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|`CAtlException` をスローします。|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。|

## <a name="atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a> AtlHresultFromLastError

呼び出し側スレッドの直前のエラー コード値を HRESULT の形式で返します。

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>解説

`AtlHresultFromLastError` を呼び出して `GetLastError` 、最後のエラーを取得し、HRESULT_FROM_WIN32 マクロを使用して HRESULT に変換した後にエラーを返します。

### <a name="requirements"></a>要件

**ヘッダー:** atlcomcli. h

## <a name="atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a> AtlHresultFromWin32

Win32 エラー コードを HRESULT に変換します。

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>パラメーター

*error*<br/>
変換するエラー値。

### <a name="remarks"></a>解説

マクロ HRESULT_FROM_WIN32 を使用して、Win32 エラーコードを HRESULT に変換します。

> [!NOTE]
> を使用する代わり `HRESULT_FROM_WIN32(GetLastError())` に、関数 [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)を使用します。

### <a name="requirements"></a>要件

**ヘッダー:** atlcomcli. h

## <a name="atlreporterror"></a><a name="atlreporterror"></a> AtlReportError

`IErrorInfo`オブジェクトのクライアントにエラー情報を提供するインターフェイスを設定します。

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

*clsid*<br/>
からエラーを報告するオブジェクトの CLSID。

*lpszDesc*<br/>
からエラーを説明する文字列。 Unicode バージョンでは、 *Lpszdesc* が LPCOLESTR 型であることが指定されています。ANSI バージョンでは、LPCSTR の種類を指定します。

*iid*<br/>
からエラーを定義するインターフェイスの IID。オペレーティングシステムによってエラーが定義されている場合は GUID_NULL します。

*hRes*<br/>
から呼び出し元に返される HRESULT。

*nID*<br/>
からエラー説明文字列が格納されているリソース識別子。 この値は、0x0200 ~ 0xFFFF の範囲で指定する必要があります。 デバッグビルドでは、 *nID* が有効な文字列にインデックスを作成しない場合、**アサート** が発生します。 リリースビルドでは、エラーの説明文字列が "不明なエラー" に設定されます。

*dwHelpID*<br/>
からエラーのヘルプコンテキスト識別子。

*lpszHelpFile*<br/>
からエラーを説明するヘルプファイルのパスと名前。

*hInst*<br/>
からリソースへのハンドル。 既定では、このパラメーターはです `__AtlBaseModuleModule::GetResourceInstance` 。ここで、 `__AtlBaseModuleModule` は [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) のグローバルインスタンス、またはそれから派生したクラスです。

### <a name="return-value"></a>戻り値

*Hres* パラメーターが0以外の場合、は *hres* の値を返します。 *Hres* が0の場合、の最初の4つのバージョンが `AtlReportError` DISP_E_EXCEPTION を返します。 最後の2つのバージョンでは、マクロ **MAKE_HRESULT (1, FACILITY_ITF,** ) の結果が返され `nID` ます。

### <a name="remarks"></a>解説

文字列 *Lpszdesc* は、エラーの説明テキストとして使用されます。 クライアントは、返された *Hres* を受け取ると、 `AtlReportError` `IErrorInfo` エラーの詳細を表す構造にアクセスできます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
> `AtlReportError`C++ の catch ハンドラーでは使用しないでください。 これらの関数の一部のオーバーライドでは、内部的に関数を使用する、ATL 文字列変換マクロを内部で使用し `_alloca` ます。 `AtlReportError`C++ の catch ハンドラーでを使用すると、c++ の catch ハンドラーで例外が発生する可能性があります。

### <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="atlthrow"></a><a name="atlthrow"></a> AtlThrow

HRESULT ステータスコードに基づいてエラーを通知するには、この関数を呼び出します。

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、エラー条件が発生した場合に ATL および MFC コードによって使用されます。 また、独自のコードから呼び出すこともできます。 この関数の既定の実装は、シンボルの定義と、プロジェクトの種類 (MFC または ATL) によって _ATL_NO_EXCEPTIONS ます。

どのような場合でも、この関数はデバッガーに対して HRESULT をトレースします。

Visual Studio 2015 Update 3 以降では、擬似 SAL の警告を回避するために、この関数には __declspec (noreturn) が付けられています。

_ATL_NO_EXCEPTIONS が MFC プロジェクトで定義されていない場合、この関数は HRESULT の値に基づいて [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md) をスローします。

ATL プロジェクトで _ATL_NO_EXCEPTIONS が定義されていない場合、関数は [CAtlException](../../atl/reference/catlexception-class.md)をスローします。

_ATL_NO_EXCEPTIONS が定義されている場合、関数は、例外をスローする代わりにアサーションエラーを発生させます。

ATL プロジェクトでは、エラーが発生した場合に ATL が使用する、この関数の独自の実装を提供できます。 これを行うには、と同じシグネチャを使用して独自の関数を定義 `AtlThrow` し、関数の名前として #define し `AtlThrow` ます。 これは、atlexcept. h を含める前に実行する必要があります (これは、atlexcept. h には atlexcept の atlexcept 含まれているため、ATL ヘッダーを含める前に実行する必要があることを意味します)。 関数に属性を使用して、 `__declspec(noreturn)` 擬似 SAL 警告を回避します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

### <a name="requirements"></a>要件

**ヘッダー:** atldef. h

## <a name="atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a> AtlThrowLastWin32

Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>解説

この関数は、の結果を `GetLastError` デバッガーにトレースします。

_ATL_NO_EXCEPTIONS が MFC プロジェクトで定義されていない場合、この関数はによって返された値に基づいて [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md) をスロー `GetLastError` します。

ATL プロジェクトで _ATL_NO_EXCEPTIONS が定義されていない場合、関数は [CAtlException](../../atl/reference/catlexception-class.md)をスローします。

_ATL_NO_EXCEPTIONS が定義されている場合、関数は、例外をスローする代わりにアサーションエラーを発生させます。

### <a name="requirements"></a>要件

**ヘッダー:** atldef. h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[デバッグとエラー報告のマクロ](../../atl/reference/debugging-and-error-reporting-macros.md)
