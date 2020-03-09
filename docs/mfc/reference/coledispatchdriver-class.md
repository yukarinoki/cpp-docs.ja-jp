---
title: COleDispatchDriver クラス
ms.date: 11/04/2016
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
ms.openlocfilehash: fa88147b57b0506f7f9ab96d4a5d2f43fdd75458
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855633"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver クラス

OLE オートメーションのクライアント側を実装します。

## <a name="syntax"></a>構文

```
class COleDispatchDriver
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[COleDispatchDriver:: COleDispatchDriver](#coledispatchdriver)|`COleDispatchDriver` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[COleDispatchDriver:: AttachDispatch](#attachdispatch)|`COleDispatchDriver` オブジェクトに `IDispatch` 接続をアタッチします。|
|[COleDispatchDriver:: CreateDispatch](#createdispatch)|`IDispatch` 接続を作成し、`COleDispatchDriver` オブジェクトにアタッチします。|
|[COleDispatchDriver::D etachDispatch](#detachdispatch)|`IDispatch` 接続を解放せずにデタッチします。|
|[COleDispatchDriver:: GetProperty](#getproperty)|オートメーションプロパティを取得します。|
|[COleDispatchDriver:: InvokeHelper](#invokehelper)|オートメーションメソッドを呼び出すためのヘルパー。|
|[COleDispatchDriver:: ReleaseDispatch](#releasedispatch)|`IDispatch` 接続を解放します。|
|[COleDispatchDriver:: SetProperty](#setproperty)|オートメーションプロパティを設定します。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[COleDispatchDriver:: operator =](#operator_eq)|ソース値を `COleDispatchDriver` オブジェクトにコピーします。|
|[COleDispatchDriver:: operator LPDISPATCH](#operator_lpdispatch)|基になる `IDispatch` ポインターにアクセスします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|説明|
|----------|-----------------|
|[COleDispatchDriver:: m_bAutoRelease](#m_bautorelease)|`ReleaseDispatch` またはオブジェクトの破棄中に `IDispatch` を解放するかどうかを指定します。|
|[COleDispatchDriver:: m_lpDispatch](#m_lpdispatch)|この `COleDispatchDriver`にアタッチされている `IDispatch` インターフェイスへのポインターを示します。|

## <a name="remarks"></a>コメント

`COleDispatchDriver` には基底クラスがありません。

OLE ディスパッチインターフェイスは、オブジェクトのメソッドとプロパティへのアクセスを提供します。 `COleDispatchDriver` のメンバー関数は、`IDispatch`型のディスパッチ接続をアタッチ、デタッチ、作成、および解放します。 その他のメンバー関数は、可変個引数リストを使用して `IDispatch::Invoke`の呼び出しを簡略化します。

このクラスは直接使用できますが、一般的には、クラスの追加ウィザードによって作成されたクラスによってのみ使用されます。 タイプライブラリをインポートC++して新しいクラスを作成する場合、新しいクラスは `COleDispatchDriver`から派生します。

`COleDispatchDriver`の使用方法の詳細については、次の記事を参照してください。

- [Automation Clients](../../mfc/automation-clients.md)

- [オートメーション サーバー](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>継承階層

`COleDispatchDriver`

## <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

##  <a name="attachdispatch"></a>COleDispatchDriver:: AttachDispatch

`AttachDispatch` メンバー関数を呼び出して、 `IDispatch` ポインターを `COleDispatchDriver` オブジェクトにアタッチします。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpDispatch*<br/>
`IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。

*bAutoRelease*<br/>
このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。

### <a name="remarks"></a>コメント

この関数は、 `IDispatch` オブジェクトに既にアタッチされている `COleDispatchDriver` ポインターを解放します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>COleDispatchDriver:: COleDispatchDriver

`COleDispatchDriver` オブジェクトを構築します。

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>パラメーター

*lpDispatch*<br/>
`IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。

*bAutoRelease*<br/>
このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。

*dispatchSrc*<br/>
既存の `COleDispatchDriver` オブジェクトへの参照。

### <a name="remarks"></a>コメント

フォーム `COleDispatchDriver`(`LPDISPATCH lpDispatch`、 **BOOL**`bAutoRelease` = **TRUE**) は、 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)インターフェイスに接続します。

フォーム `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) は、既存の `COleDispatchDriver` オブジェクトをコピーし、参照カウントをインクリメントします。

フォーム `COleDispatchDriver`() は `COleDispatchDriver` オブジェクトを作成しますが、`IDispatch` インターフェイスには接続しません。 引数を指定せずに `COleDispatchDriver`() を使用する前に、 [COleDispatchDriver:: CreateDispatch](#createdispatch)または[COleDispatchDriver:: attachdispatch](#attachdispatch)を使用して、`IDispatch` をそれに接続する必要があります。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](#createdispatch)の例を参照してください。

##  <a name="createdispatch"></a>COleDispatchDriver:: CreateDispatch

[IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) インターフェイス オブジェクトを作成して `COleDispatchDriver` オブジェクトにアタッチします。

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
作成する `IDispatch` 接続オブジェクトのクラス ID。

*pError*<br/>
作成の結果ステータス コードを格納する OLE 例外オブジェクトへのポインター。

*lpszProgID*<br/>
ディスパッチ オブジェクトが作成されるオートメーション オブジェクトの"Excel.Document.5"などのプログラム ID へのポインター。

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>COleDispatchDriver::D etachDispatch

現在の `IDispatch` 接続をこのオブジェクトからデタッチします。

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>戻り値

以前にアタッチされた OLE `IDispatch` オブジェクトへのポインター。

### <a name="remarks"></a>コメント

`IDispatch` が解放されていません。

LPDISPATCH の種類の詳細については、「Windows SDK での[IDispatch インターフェイスの実装](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>COleDispatchDriver:: GetProperty

*Dwdispid*によって指定されたオブジェクトプロパティを取得します。

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>パラメーター

*dwDispID*<br/>
取得するプロパティを識別します。

*vtProp*<br/>
取得するプロパティを指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](#invokehelper)の「解説」をご覧ください。

*pvProp*<br/>
プロパティ値を受け取る変数のアドレス。 *VtProp*によって指定された型と一致している必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>COleDispatchDriver:: InvokeHelper

*Wflags*によって指定されたコンテキストで、 *dwdispid*によって指定されたオブジェクトメソッドまたはプロパティを呼び出します。

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>パラメーター

*dwDispID*<br/>
呼び出されるメソッドまたはプロパティを識別します。

*wFlags*<br/>
`IDispatch::Invoke`の呼び出しのコンテキストを記述するフラグ。 。 使用可能な値の一覧については、Windows SDK の[IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)の*wflags*パラメーターを参照してください。

*vtRet*<br/>
戻り値の型を指定します。 使用可能な値については、「解説」を参照してください。

*pvRet*<br/>
プロパティ値または戻り値を受け取る変数のアドレス。 これは、 *Vtret*によって指定された型と一致している必要があります。

*pbParamInfo*<br/>
*Pbparaminfo*に続くパラメーターの型を指定する、null で終わる文字列のバイトを指すポインター。

*[...]*<br/>
*Pbparaminfo*で指定された型のパラメーターの変数リスト。

### <a name="remarks"></a>コメント

*Pbparaminfo*パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 引数の変数一覧は、構文宣言では、 **...** で表されます。

*Vtret*引数に使用できる値は、varenum 列挙体から取得されます。 次の値を指定できます。

|シンボル|戻り値の型|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**暦年**|
|VT_DATE|**DATE**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**型**|
|VT_UNKNOWN|LPUNKNOWN|

*Pbparaminfo*引数は**VTS_** 定数のスペース区切りのリストです。 スペース (コンマではない) で区切られるこれらの値の 1 つ以上は、関数のパラメーター リストを指定します。 使用可能な値は、 [EVENT_CUSTOM](event-maps.md#event_custom) マクロで一覧表示されます。

この関数は、パラメーターを VARIANTARG 値に変換し、 [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)メソッドを呼び出します。 `Invoke` の呼び出しに失敗すると、この関数は、例外をスローします。 `IDispatch::Invoke` によって返された SCODE (状態コード) が DISP_E_EXCEPTION の場合、この関数は[COleException](../../mfc/reference/coleexception-class.md)オブジェクトをスローします。それ以外の場合は、 [COleDispatchException](../../mfc/reference/coledispatchexception-class.md)をスローします。

詳細については、「 [VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant)」、「 [idispatch インターフェイスの実装](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」、「 [idispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)」、および「Windows SDK での[COM エラーコードの構造](/windows/win32/com/structure-of-com-error-codes)」を参照してください。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](#createdispatch)の例を参照してください。

##  <a name="m_bautorelease"></a>COleDispatchDriver:: m_bAutoRelease

TRUE の場合、 [m_lpDispatch](#m_lpdispatch)によってアクセスされる COM オブジェクトは、 [releasedispatch](#releasedispatch)が呼び出されるか、この `COleDispatchDriver` オブジェクトが破棄されるときに、自動的に解放されます。

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>コメント

既定では、コンストラクターで `m_bAutoRelease` が TRUE に設定されています。

COM オブジェクトの解放の詳細については、「Windows SDK での[参照カウントの実装](/windows/win32/com/implementing-reference-counting)」および「 [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>COleDispatchDriver:: m_lpDispatch

この `COleDispatchDriver`にアタッチされている `IDispatch` インターフェイスへのポインター。

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>コメント

`m_lpDispatch` データメンバーは、LPDISPATCH 型のパブリック変数です。

詳細については、Windows SDK の「 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 」を参照してください。

### <a name="example"></a>例

  [COleDispatchDriver:: AttachDispatch](#attachdispatch)の例を参照してください。

##  <a name="operator_eq"></a>COleDispatchDriver:: operator =

ソース値を `COleDispatchDriver` オブジェクトにコピーします。

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>パラメーター

*dispatchSrc*<br/>
既存の `COleDispatchDriver` オブジェクトへのポインター。

##  <a name="operator_lpdispatch"></a>COleDispatchDriver:: operator LPDISPATCH

`COleDispatchDriver` オブジェクトの基になる `IDispatch` ポインターにアクセスします。

```
operator LPDISPATCH();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>COleDispatchDriver:: ReleaseDispatch

`IDispatch` 接続を解放します。 詳細については、「 [IDispatch インターフェイスの実装](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

```
void ReleaseDispatch();
```

### <a name="remarks"></a>コメント

自動リリースがこの接続に対して設定されている場合、この関数は、インターフェイスを解放する前に `IDispatch::Release` を呼び出します。

### <a name="example"></a>例

  [COleDispatchDriver:: AttachDispatch](#attachdispatch)の例を参照してください。

##  <a name="setproperty"></a>COleDispatchDriver:: SetProperty

*Dwdispid*によって指定された OLE オブジェクトプロパティを設定します。

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>パラメーター

*dwDispID*<br/>
設定するプロパティを識別します。

*vtProp*<br/>
設定するプロパティの型を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](#invokehelper)の「解説」をご覧ください。

*[...]*<br/>
*VtProp*によって指定された型の1つのパラメーター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>参照

[MFC のサンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
