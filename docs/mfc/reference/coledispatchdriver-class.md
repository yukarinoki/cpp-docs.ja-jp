---
title: クラスをディスパッチします。
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
ms.openlocfilehash: c22097c3a686857a6a5698033b7395c5d15f2570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366077"
---
# <a name="coledispatchdriver-class"></a>クラスをディスパッチします。

OLE オートメーションのクライアント側を実装します。

## <a name="syntax"></a>構文

```
class COleDispatchDriver
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を返します。](#coledispatchdriver)|`COleDispatchDriver` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をディスパッチします。](#attachdispatch)|オブジェクトに`IDispatch`接続を`COleDispatchDriver`アタッチします。|
|[を呼び出します。](#createdispatch)|接続を`IDispatch`作成し、オブジェクトに`COleDispatchDriver`アタッチします。|
|[ディスパッチドライバー::Dエタッハディスパッチ](#detachdispatch)|接続を`IDispatch`解放せずに、接続をデタッチします。|
|[を返します。](#getproperty)|オートメーション プロパティを取得します。|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|オートメーション メソッドを呼び出すヘルパー。|
|[を返します。](#releasedispatch)|接続を`IDispatch`解放します。|
|[を返します。](#setproperty)|オートメーション プロパティを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を返すドライバー::演算子 =](#operator_eq)|ソース値をオブジェクトに`COleDispatchDriver`コピーします。|
|[を呼び出します。](#operator_lpdispatch)|基になる`IDispatch`ポインターにアクセスします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ディスパッチドライバー::m_bAutoRelease](#m_bautorelease)|破棄中`ReleaseDispatch`またはオブジェクトの`IDispatch`破棄を解放するかどうかを指定します。|
|[ディスパッチドライバー::m_lpDispatch](#m_lpdispatch)|この`IDispatch``COleDispatchDriver`にアタッチされたインターフェイスへのポインターを示します。|

## <a name="remarks"></a>解説

`COleDispatchDriver`は基本クラスを持っていません。

OLE ディスパッチ インターフェイスは、オブジェクトのメソッドとプロパティにアクセスします。 型`IDispatch`のディスパッチ`COleDispatchDriver`接続をアタッチ、デタッチ、作成、および解放するメンバー関数。 他のメンバー関数は、変数引数リストを`IDispatch::Invoke`使用して、 の呼び出しを簡単にします。

このクラスは直接使用できますが、通常はクラスの追加ウィザードで作成されたクラスでのみ使用されます。 タイプ ライブラリをインポートして新しい C++ クラスを作成すると、新しいクラス`COleDispatchDriver`が から派生します。

の使用方法`COleDispatchDriver`の詳細については、次の記事を参照してください。

- [オートメーション クライアント](../../mfc/automation-clients.md)

- [オートメーション サーバー](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>継承階層

`COleDispatchDriver`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="coledispatchdriverattachdispatch"></a><a name="attachdispatch"></a>をディスパッチします。

`AttachDispatch` メンバー関数を呼び出して、 `IDispatch` ポインターを `COleDispatchDriver` オブジェクトにアタッチします。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>パラメーター

*を割り出す*<br/>
`IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。

*b自動リリース*<br/>
このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。

### <a name="remarks"></a>解説

この関数は、 `IDispatch` オブジェクトに既にアタッチされている `COleDispatchDriver` ポインターを解放します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

## <a name="coledispatchdrivercoledispatchdriver"></a><a name="coledispatchdriver"></a>を返します。

`COleDispatchDriver` オブジェクトを構築します。

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>パラメーター

*を割り出す*<br/>
`IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。

*b自動リリース*<br/>
このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。

*ディスパッチスrc*<br/>
既存`COleDispatchDriver`のオブジェクトへの参照。

### <a name="remarks"></a>解説

フォーム`COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) は[IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)インターフェイスを接続します。

form `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`)`COleDispatchDriver`は、既存のオブジェクトをコピーし、参照カウントをインクリメントします。

フォーム`COleDispatchDriver`( )`COleDispatchDriver`はオブジェクトを作成しますが`IDispatch`、インターフェイスを接続しません。 引数なしで`COleDispatchDriver`( ) を使用`IDispatch`する前に[、COleDispatchDriver::CreateDispatch ドライバー](#createdispatch)または[COleDispatch ドライバー::アタッチディスパッチ](#attachdispatch)のいずれかを使用してに接続する必要があります。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](#createdispatch)の例を参照してください。

## <a name="coledispatchdrivercreatedispatch"></a><a name="createdispatch"></a>を呼び出します。

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

*Clsid*<br/>
作成する `IDispatch` 接続オブジェクトのクラス ID。

*pError*<br/>
作成の結果ステータス コードを格納する OLE 例外オブジェクトへのポインター。

*をクリックします。*<br/>
ディスパッチ オブジェクトが作成されるオートメーション オブジェクトの"Excel.Document.5"などのプログラム ID へのポインター。

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

## <a name="coledispatchdriverdetachdispatch"></a><a name="detachdispatch"></a>ディスパッチドライバー::Dエタッハディスパッチ

現在`IDispatch`の接続をこのオブジェクトから切り離します。

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>戻り値

以前にアタッチされた OLE`IDispatch`オブジェクトへのポインター。

### <a name="remarks"></a>解説

は`IDispatch`リリースされません。

LPDISPATCH 型の詳細については、「Windows SDK[での IDispatch インターフェイスの実装](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

## <a name="coledispatchdrivergetproperty"></a><a name="getproperty"></a>を返します。

*dwDispID*で指定されたオブジェクト プロパティを取得します。

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
取得するプロパティを識別します。

*vtプロップ*<br/>
取得するプロパティを指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](#invokehelper)の「解説」をご覧ください。

*pv プロップ*<br/>
プロパティ値を受け取る変数のアドレス。 vtProp で指定された型*vtProp*と一致する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

## <a name="coledispatchdriverinvokehelper"></a><a name="invokehelper"></a>を呼び出します。

*dwDispID*で指定されたオブジェクト メソッドまたはプロパティを *、wFlags*で指定されたコンテキストで呼び出します。

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
呼び出されるメソッドまたはプロパティを識別します。

*wフラグ*<br/>
への呼び出しのコンテキストを記述`IDispatch::Invoke`するフラグ。 . 可能な値の一覧については、Windows SDK の*wFlags*パラメーターを参照してください。 [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)

*vtRet*<br/>
戻り値の型を指定します。 使用可能な値については、「解説」を参照してください。

*pvRet*<br/>
プロパティ値または戻り値を受け取る変数のアドレス。 *vtRet*で指定された型と一致する必要があります。

*パラムインフォ*<br/>
*pbParamInfo*に続くパラメーターの型を指定する、null で終わるバイトの文字列へのポインター。

*...*<br/>
パラメーターの変数リスト、 *pbParamInfo*で指定された型のリスト。

### <a name="remarks"></a>解説

*pbParamInfo*パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 引数の変数一覧は、構文宣言では、 **...** で表されます。

*vtRet*引数に指定できる値は、VARENUM 列挙体から取得されます。 使用できる値は次のとおりです。

|Symbol|戻り値の型|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**長い**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**日付**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPディスパッチ|
|VT_ERROR|SCODE|
|VT_BOOL|**Bool**|
|VT_VARIANT|**バリアント**|
|VT_UNKNOWN|LPUNKNOWN|

*引数 pbParamInfo*は **、VTS_** 定数の一覧をスペースで区切ったものです。 スペース (コンマではない) で区切られるこれらの値の 1 つ以上は、関数のパラメーター リストを指定します。 使用可能な値は、 [EVENT_CUSTOM](event-maps.md#event_custom) マクロで一覧表示されます。

この関数は、パラメータを VARIANTARG 値に変換し、その後、 [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) メソッドを呼び出します。 `Invoke` の呼び出しに失敗すると、この関数は、例外をスローします。 によって`IDispatch::Invoke`返される SCODE (状態コード) がDISP_E_EXCEPTION場合、この関数は[COleException](../../mfc/reference/coleexception-class.md)オブジェクトをスローします。それ以外の場合は[、COleDispatch 例外を](../../mfc/reference/coledispatchexception-class.md)スローします。

詳細については[、「VariantARG](/windows/win32/api/oaidl/ns-oaidl-variant) [」、IDispatch インターフェイスの実装](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)[、IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)、および Windows SDK の[COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](#createdispatch)の例を参照してください。

## <a name="coledispatchdriverm_bautorelease"></a><a name="m_bautorelease"></a>ディスパッチドライバー::m_bAutoRelease

TRUE の場合[、m_lpDispatch](#m_lpdispatch)によってアクセスされる COM オブジェクトは[、ReleaseDispatch](#releasedispatch)が呼び`COleDispatchDriver`出されたとき、またはこのオブジェクトが破棄されたときに自動的に解放されます。

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>解説

既定では、`m_bAutoRelease`コンストラクターでは TRUE に設定されます。

COM オブジェクトのリリースの詳細については、「[参照カウントの実装](/windows/win32/com/implementing-reference-counting)」および[「IUnknown::Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) (Windows SDK)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

## <a name="coledispatchdriverm_lpdispatch"></a><a name="m_lpdispatch"></a>ディスパッチドライバー::m_lpDispatch

に`IDispatch``COleDispatchDriver`アタッチされたインターフェイスへのポインター。

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>解説

データ`m_lpDispatch`メンバーは、LPDISPATCH 型のパブリック変数です。

詳細については、Windows SDK[の IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)を参照してください。

### <a name="example"></a>例

  の例[を](#attachdispatch)参照してください。

## <a name="coledispatchdriveroperator-"></a><a name="operator_eq"></a>を返すドライバー::演算子 =

ソース値をオブジェクトに`COleDispatchDriver`コピーします。

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>パラメーター

*ディスパッチスrc*<br/>
既存`COleDispatchDriver`のオブジェクトへのポインター。

## <a name="coledispatchdriveroperator-lpdispatch"></a><a name="operator_lpdispatch"></a>を呼び出します。

オブジェクトの基になる`IDispatch`ポインターに`COleDispatchDriver`アクセスします。

```
operator LPDISPATCH();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

## <a name="coledispatchdriverreleasedispatch"></a><a name="releasedispatch"></a>を返します。

接続を`IDispatch`解放します。 詳細については、[次を参照してください IDispatch インターフェイスの実装](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>解説

この接続に対して自動解放が設定されている場合、この`IDispatch::Release`関数はインタフェースを解放する前に呼び出します。

### <a name="example"></a>例

  の例[を](#attachdispatch)参照してください。

## <a name="coledispatchdriversetproperty"></a><a name="setproperty"></a>を返します。

*dwDispID*で指定された OLE オブジェクト プロパティを設定します。

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
設定するプロパティを識別します。

*vtプロップ*<br/>
設定するプロパティの型を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](#invokehelper)の「解説」をご覧ください。

*...*<br/>
*vtProp*で指定された型の単一のパラメーター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
