---
title: エラー報告に関するグローバル関数のデバッグと |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb3257b5205587b27a83671ed8e610aad5373eef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364883"
---
# <a name="debugging-and-error-reporting-global-functions"></a>デバッグとエラー報告に関するグローバル関数
これらの関数は、デバッグとトレースに役立つ機能を提供します。  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|返します、 `GetLastError` HRESULT の形式でのエラー コード。|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 エラー コードを HRESULT に変換します。|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|設定**IErrorInfo**をクライアントにエラーの詳細を提供します。|  
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|`CAtlException` をスローします。|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。|  
  
##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError  
 呼び出し側スレッドの直前のエラー コード値を HRESULT の形式で返します。  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>コメント  
 `AtlHresultFromLastError` 呼び出し`GetLastError`を最後のエラーを取得しを使用して、HRESULT に変換した後、エラーを返します、 **HRESULT_FROM_WIN32**マクロです。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32  
 Win32 エラー コードを HRESULT に変換します。  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>パラメーター  
 *error*  
 変換するエラー値。  
  
### <a name="remarks"></a>コメント  
 Win32 エラー コードをマクロを使用して、HRESULT に変換**HRESULT_FROM_WIN32**です。  
  
> [!NOTE]
>  使用せずに**HRESULT_FROM_WIN32(GetLastError())**、関数を使用して[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)です。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  

##  <a name="atlreporterror"></a>  AtlReportError  
 設定、`IErrorInfo`エラー情報をクライアントに提供されたオブジェクトのインターフェイスです。  
  
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
 `clsid`  
 [in]エラーを報告するオブジェクトの CLSID。  
  
 `lpszDesc`  
 [in]エラーを説明する文字列。 Unicode バージョンを指定する`lpszDesc`の種類は**LPCOLESTR**; ANSI バージョンの種類を指定する`LPCSTR`です。  
  
 `iid`  
 [in]エラーを定義するインターフェイスの IID または`GUID_NULL`場合は、エラーは、オペレーティング システムによって定義されます。  
  
 `hRes`  
 [in]`HRESULT`する呼び出し元に返されます。  
  
 `nID`  
 [in]エラーを説明する文字列が格納されているリソースの識別子。 この値は、包括的 0x0200 と 0 xffff、間にする必要があります。 デバッグ ビルドで、 **ASSERT**なります`nID`有効な文字列のインデックスは作成されません。 リリース ビルドでエラーを説明する文字列を「不明なエラー」に設定されます。  
  
 `dwHelpID`  
 [in]エラーのヘルプ コンテキスト id。  
  
 `lpszHelpFile`  
 [in]パスとエラーを説明するヘルプ ファイルの名前。  
  
 `hInst`  
 [in]リソースへのハンドル。 このパラメーターは、既定では、 **__AtlBaseModuleModule::GetResourceInstance**ここで、 **__AtlBaseModuleModule**のグローバル インスタンスは、 [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)またはクラス派生します。  
  
### <a name="return-value"></a>戻り値  
 場合、`hRes`パラメーターが 0 以外の場合の値を返します`hRes`です。 場合`hRes`が 0 の場合、最初の 4 つのバージョンの`AtlReportError`返す`DISP_E_EXCEPTION`です。 最後の 2 つのバージョンは、マクロの結果を返す**MAKE_HRESULT (1, FACILITY_ITF、** `nID` **)** です。  
  
### <a name="remarks"></a>コメント  
 文字列*lpszDesc*エラーの説明テキストとして使用されます。 クライアントが受信すると、`hRes`から返す`AtlReportError`、クライアントがアクセスできる、 **IErrorInfo**エラーの詳細構造です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  使用しないでください`AtlReportError`C++ では catch ハンドラー。 これらの関数のいくつかのオーバーライドを使用して ATL 文字列変換マクロ内部的には、使用される、`_alloca`内部的に機能します。 使用して`AtlReportError`C++ catch ハンドラー C++ catch ハンドラーで例外が発生することができます。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
    
##  <a name="atlthrow"></a>  AtlThrow  
 `HRESULT` ステータス コードに基づいてエラーを通知します。  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>パラメーター  
 `hr`  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 この関数はエラーが発生した場合、ATL および MFC コードによって使用されます。 独自のコードから呼び出すこともできます。 この関数の既定の実装は、シンボルの定義によって異なります**シンボル**や MFC または atl プロジェクトの種類。  
  
 すべてのケースでは、この関数は、デバッガーが HRESULT をトレースします。  
  
 Visual Studio 2015 Update 3 以降では、この関数は、誤った SAL 警告を回避する属性付き __declspec(noreturn) です。  
  
 場合**シンボル**が定義されていない MFC プロジェクトでは、この関数がスローされます、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md) HRESULT の値に基づきます。  
  
 場合**シンボル**関数がスローされます、ATL プロジェクトで定義されていない、 [CAtlException](../../atl/reference/catlexception-class.md)です。  
  
 場合**シンボル**が定義されている場合、関数が例外をスローする代わりに、アサーションの失敗します。  
  
 ATL プロジェクトの場合は、障害が発生した場合、ATL で使用するには、この関数の実装を提供することです。 これを行うには、定義、独自の関数と同じシグネチャを持つ`AtlThrow`と #define`AtlThrow`関数の名前を指定します。 これは、atlexcept.h (つまり atlbase.h に atlexcept.h が含まれているために、ATL ヘッダーをインクルードする前に行う必要があります) を含める前に行う必要があります。 属性の関数の`__declspec(noreturn)`を誤った SAL 警告を回避します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldef.h  

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32  
 Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>コメント  
 この関数の結果をトレースする`GetLastError`デバッガーにします。  
  
 場合**シンボル**が定義されていない MFC プロジェクトでは、この関数がスローされます、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md) によって返される値に基づく`GetLastError`.  
  
 場合**シンボル**関数がスローされます、ATL プロジェクトで定義されていない、 [CAtlException](../../atl/reference/catlexception-class.md)です。  
  
 場合**シンボル**が定義されている場合、関数が例外をスローする代わりに、アサーションの失敗します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldef.h  
   
     
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)   
 [デバッグとエラー報告に関するマクロ](../../atl/reference/debugging-and-error-reporting-macros.md)









