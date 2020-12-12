---
description: '詳細については、「テクニカルノート 65: Dual-Interface OLE オートメーションサーバーのサポート」を参照してください。'
title: 'テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート'
ms.date: 06/28/2018
f1_keywords:
- vc.ole
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
ms.openlocfilehash: 9add7b42c832944c10b4b607f26b6ca8f23ae300
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214573"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、MFC ベースの OLE オートメーションサーバーアプリケーションにデュアルインターフェイスサポートを追加する方法について説明します。 [Acdual](../overview/visual-cpp-samples.md)サンプルは、デュアルインターフェイスのサポートを示しています。このメモのコード例は、acdual から取得されています。 このメモに記載されているマクロ (DECLARE_DUAL_ERRORINFO、DUAL_ERRORINFO_PART、IMPLEMENT_DUAL_ERRORINFO など) は、ACDUAL のサンプルに含まれており、MFCDUAL. H にあります。

## <a name="dual-interfaces"></a>デュアルインターフェイス

OLE オートメーションで `IDispatch` は、インターフェイス、VTBL インターフェイス、またはデュアルインターフェイス (両方を含む) を実装することができますが、公開されているすべての OLE オートメーションオブジェクトに対してデュアルインターフェイスを実装することを強くお勧めします。 デュアルインターフェイス `IDispatch` には、または VTBL 専用のインターフェイスよりも大きな利点があります。

- バインディングは、コンパイル時に VTBL インターフェイスまたは実行時に実行さ `IDispatch` れます。

- VTBL インターフェイスを使用できる OLE オートメーションコントローラーは、パフォーマンスの向上によってメリットが得られる場合があります。

- インターフェイスを使用する既存の OLE オートメーションコントローラー `IDispatch` は、引き続き機能します。

- VTBL インターフェイスは、C++ からより簡単に呼び出すことができます。

- Visual Basic オブジェクトサポート機能との互換性を確保するには、デュアルインターフェイスが必要です。

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget-Based クラスへの Dual-Interface サポートの追加

デュアルインターフェイスは、から派生したカスタムインターフェイスにすぎ `IDispatch` ません。 ベースのクラスでデュアルインターフェイスサポートを実装する最も簡単 `CCmdTarget` な方法は、最初に MFC と ClassWizard を使用してクラスに通常のディスパッチインターフェイスを実装してから、後でカスタムインターフェイスを追加することです。 ほとんどの場合、カスタムインターフェイスの実装は、単純に MFC 実装に戻り `IDispatch` ます。

まず、サーバーの ODL ファイルを変更して、オブジェクトのデュアルインターフェイスを定義します。 デュアルインターフェイスを定義するには、Visual C++ ウィザードによって生成されるステートメントではなく、インターフェイスステートメントを使用する必要があり `DISPINTERFACE` ます。 既存のステートメントを削除するのではなく `DISPINTERFACE` 、新しい interface ステートメントを追加します。 フォームを保持することで `DISPINTERFACE` 、引き続き ClassWizard を使用してオブジェクトにプロパティとメソッドを追加できますが、インターフェイスステートメントには、同等のプロパティとメソッドを追加する必要があります。

デュアルインターフェイスのインターフェイスステートメントには、 *OLEAUTOMATION* および *dual* 属性が含まれている必要があり、インターフェイスはから派生する必要があり `IDispatch` ます。 [Guidgen.exe](../overview/visual-cpp-samples.md)サンプルを使用して、デュアルインターフェイスの **IID** を作成できます。

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Interface ステートメントを配置したら、メソッドとプロパティのエントリを追加します。 デュアルインターフェイスの場合は、パラメーターリストを再配置して、デュアルインターフェイスのメソッドとプロパティアクセサー関数が **HRESULT** を返し、その戻り値をパラメーターとして属性として渡すようにする必要があり `[retval,out]` ます。 プロパティについては、read ( `propget` ) アクセス関数と write ( `propput` ) アクセス関数の両方を同じ id で追加する必要があることに注意してください。例えば：

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

メソッドとプロパティを定義したら、コクラスステートメントで interface ステートメントへの参照を追加する必要があります。 次に例を示します。

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

ODL ファイルが更新されたら、MFC のインターフェイスマップ機構を使用して、オブジェクトクラスのデュアルインターフェイスの実装クラスを定義し、対応するエントリを MFC の機構で作成し `QueryInterface` ます。 `INTERFACE_PART`ODL の interface ステートメントの各エントリに対して、ブロック内に1つのエントリと、ディスパッチインターフェイスのエントリが必要です。 *Propput* 属性を持つ各 ODL エントリには、という名前の関数が必要 `put_propertyname` です。 *Propget* 属性を持つ各エントリには、という名前の関数が必要 `get_propertyname` です。

デュアルインターフェイスの実装クラスを定義するには、 `DUAL_INTERFACE_PART` オブジェクトクラス定義にブロックを追加します。 次に例を示します。

```cpp
BEGIN_DUAL_INTERFACE_PART(DualAClick, IDualAClick)
    STDMETHOD(put_text)(THIS_ BSTR newText);
    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);
    STDMETHOD(put_x)(THIS_ short newX);
    STDMETHOD(get_x)(THIS_ short FAR* retval);
    STDMETHOD(put_y)(THIS_ short newY);
    STDMETHOD(get_y)(THIS_ short FAR* retval);
    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);
    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);
    STDMETHOD(RefreshWindow)(THIS);
    STDMETHOD(SetAllProps)(THIS_ short x, short y, BSTR text);
    STDMETHOD(ShowWindow)(THIS);
END_DUAL_INTERFACE_PART(DualAClick)
```

デュアルインターフェイスを MFC の [QueryInterface](/windows/win32/com/queryinterface--navigating-in-an-object) 機構に接続するには、 `INTERFACE_PART` インターフェイスマップにエントリを追加します。

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

次に、インターフェイスの実装に入力する必要があります。 ほとんどの場合、既存の MFC 実装に委任することができ `IDispatch` ます。 次に例を示します。

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);
    return lpDispatch->GetTypeInfoCount(pctinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID FAR* rgdispid)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames, lcid, rgdispid);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS FAR* pdispparams,
    VARIANT FAR* pvarResult,
    EXCEPINFO FAR* pexcepinfo,
    UINT FAR* puArgErr)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember, riid, lcid,
        wFlags, pdispparams, pvarResult, pexcepinfo, puArgErr);
}
```

オブジェクトのメソッドとプロパティアクセサー関数の場合は、実装に入力する必要があります。 通常、メソッドとプロパティ関数は、ClassWizard を使用して生成されたメソッドにデリゲートを返すことができます。 ただし、変数に直接アクセスするためのプロパティを設定する場合は、変数に値を取得/配置するコードを記述する必要があります。 次に例を示します。

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Unicode BSTR to
    // Ansi CString, if necessary...
    pThis->m_str = newText;
    return NOERROR;
}

STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Ansi CString to
    // Unicode BSTR, if necessary...
    pThis->m_str.SetSysString(retval);
    return NOERROR;
}
```

## <a name="passing-dual-interface-pointers"></a>Dual-Interface ポインターを渡す

デュアルインターフェイスポインターを渡すことは、特にを呼び出す必要がある場合は、簡単ではありません `CCmdTarget::FromIDispatch` 。 `FromIDispatch` は、MFC のポインターに対してのみ機能 `IDispatch` します。 これを回避する方法の1つ `IDispatch` として、MFC によって設定された元のポインターを照会し、それを必要とする関数にそのポインターを渡す方法があります。 次に例を示します。

```
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(
    IDualAutoClickPoint FAR* newPosition)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp = NULL;
    newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);
    pThis->SetPosition(lpDisp);
    lpDisp->Release();
    return NOERROR;
}
```

デュアルインターフェイスメソッドを使用してポインターを戻す前に、MFC `IDispatch` ポインターからデュアルインターフェイスポインターに変換することが必要になる場合があります。 次に例を示します。

```
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(
    IDualAutoClickPoint FAR* FAR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp;
    lpDisp = pThis->GetPosition();
    lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);
    return NOERROR;
}
```

## <a name="registering-the-applications-type-library"></a>アプリケーションのタイプライブラリを登録しています

AppWizard は、OLE オートメーションサーバーアプリケーションのタイプライブラリをシステムに登録するコードを生成しません。 タイプライブラリを登録する方法は他にもありますが、アプリケーションが OLE 型情報を更新するときにタイプライブラリを登録すると便利です。つまり、アプリケーションがスタンドアロンで実行されるときには、そのタイプライブラリを登録すると便利です。

アプリケーションがスタンドアロンで実行されるときに、アプリケーションのタイプライブラリを登録するには、次のようにします。

- AFXCTL.H を含めます。標準の H には、ヘッダーファイル STDAFX.H が含まれています。H 関数の定義にアクセスするために使用 `AfxOleRegisterTypeLib` します。

- アプリケーションの関数で `InitInstance` 、への呼び出しを見つけ `COleObjectFactory::UpdateRegistryAll` ます。 この呼び出しの後に、タイプライブラリ `AfxOleRegisterTypeLib` に対応する **LIBID** と、タイプライブラリの名前を指定して、への呼び出しを追加します。

    ```cpp
    // When a server application is launched stand-alone, it is a good idea
    // to update the system registry in case it has been damaged.
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

    COleObjectFactory::UpdateRegistryAll();

    // DUAL_SUPPORT_START
        // Make sure the type library is registered or dual interface won't work.
        AfxOleRegisterTypeLib(AfxGetInstanceHandle(),
            LIBID_ACDual,
            _T("AutoClik.TLB"));
    // DUAL_SUPPORT_END
    ```

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>タイプライブラリの変更に対応するようにプロジェクトのビルド設定を変更する

タイプライブラリが再構築されるたびに、 **UUID** 定義を含むヘッダーファイルが MkTypLib によって生成されるように、プロジェクトのビルド設定を変更するには、次のようにします。

1. [ **ビルド** ] メニューの [ **設定**] をクリックし、各構成の [ファイル] ボックスの一覧から ODL ファイルを選択します。

2. [ **OLE の種類** ] タブをクリックし、[ **出力ヘッダー** ファイル名] フィールドにファイル名を指定します。 MkTypLib によって既存のファイルが上書きされるので、プロジェクトで使用されていないファイル名を使用します。 [ **OK]** をクリックして、[ **ビルドの設定** ] ダイアログボックスを閉じます。

MkTypLib によって生成されたヘッダーファイルからプロジェクトに **UUID** 定義を追加するには、次のようにします。

1. MkTypLib によって生成されるヘッダーファイルを標準のヘッダーファイル *stdafx.h* にインクルードします。

2. 新しいファイル INITIIDS を作成します。CPP を使用し、プロジェクトに追加します。 このファイルには、OLE2 を含めた後に、MkTypLib で生成されたヘッダーファイルを含めます。H と INITGUID。始め

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. [ **ビルド** ] メニューの [ **設定**] をクリックし、[initiids] を選択します。各構成のファイルリストからの CPP。

4. [ **C++** ] タブをクリックし、[Category **プリコンパイル済みヘッダー**] をクリックして、[ **プリコンパイル済みヘッダーを使用しない** ] オプションボタンを選択します。 [OK] をクリックして、[ **ビルドの設定** ] ダイアログボックスを閉じます。

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>タイプライブラリでの正しいオブジェクトクラス名の指定

に付属しているウィザードでは、実装クラス名を誤って使用して、OLE 作成可能なクラス用のサーバーの ODL ファイル内のコクラスを指定して Visual C++ ます。 これは機能しますが、実装クラス名は、オブジェクトのユーザーが使用するクラス名ではない場合があります。 正しい名前を指定するには、ODL ファイルを開き、各コクラスステートメントを見つけて、実装クラス名を正しい外部名に置き換えます。

Coclass ステートメントが変更されると、MkTypLib によって生成されるヘッダーファイル内の **CLSID** の変数名がそれに応じて変更されることに注意してください。 新しい変数名を使用するには、コードを更新する必要があります。

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>例外とオートメーションエラーインターフェイスの処理

オートメーションオブジェクトのメソッドとプロパティアクセサー関数は、例外をスローする場合があります。 その場合は、それらをデュアルインターフェイスの実装で処理し、例外に関する情報を OLE オートメーションのエラー処理インターフェイス () を使用してコントローラーに渡す必要があり `IErrorInfo` ます。 このインターフェイスは、および VTBL インターフェイスの両方を介して、詳細なコンテキストエラー情報を提供し `IDispatch` ます。 エラーハンドラーが使用可能であることを示すには、インターフェイスを実装する必要があり `ISupportErrorInfo` ます。

エラー処理機構を示すために、標準ディスパッチサポートを実装するために使用される ClassWizard で生成された関数が例外をスローするとします。 MFC のの実装で `IDispatch::Invoke` は、通常、これらの例外をキャッチし、呼び出しによって返される EXCEPTINFO 構造体に変換し `Invoke` ます。 ただし、VTBL インターフェイスを使用する場合は、自分で例外をキャッチする必要があります。 デュアルインターフェイスのメソッドを保護する例を次に示します。

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    TRY_DUAL(IID_IDualAClick)
    {
        // MFC automatically converts from Unicode BSTR to
        // Ansi CString, if necessary...
        pThis->m_str = newText;
        return NOERROR;
    }
    CATCH_ALL_DUAL
}
```

`CATCH_ALL_DUAL` は、例外が発生したときに正しいエラーコードを返すようにします。 `CATCH_ALL_DUAL` インターフェイスを使用して、MFC 例外を OLE オートメーションエラー処理情報に変換し `ICreateErrorInfo` ます。 (例の `CATCH_ALL_DUAL` マクロは、MFCDUAL というファイルにあります。「 [ACDUAL](../overview/visual-cpp-samples.md) サンプルの H」。 例外を処理するために呼び出す関数は、 `DualHandleException` ファイルの MFCDUAL にあります。CPP) `CATCH_ALL_DUAL` 発生した例外の種類に基づいて返されるエラーコードを決定します。

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) -この場合、 `HRESULT` は次のコードを使用して構築されます。

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

   これにより、 `HRESULT` 例外の原因となったインターフェイスに固有のが作成されます。 エラーコードは0x200 によってオフセットされ、標準 OLE インターフェイスのシステム定義のと競合しないようにし `HRESULT` ます。

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) -この場合は、 `E_OUTOFMEMORY` が返されます。

- その他の例外-この場合 `E_UNEXPECTED` は、が返されます。

OLE オートメーションエラーハンドラーが使用されていることを示すには、インターフェイスも実装する必要があり `ISupportErrorInfo` ます。

まず、オートメーションクラス定義にコードを追加して、がサポートするように `ISupportErrorInfo` します。

次に、オートメーションクラスのインターフェイスマップにコードを追加して、 `ISupportErrorInfo` 実装クラスを MFC の機構に関連付け `QueryInterface` ます。 ステートメントは、 `INTERFACE_PART` に対して定義されているクラスと一致し `ISupportErrorInfo` ます。

最後に、をサポートするように定義されているクラスを実装し `ISupportErrorInfo` ます。

( [ACDUAL](../overview/visual-cpp-samples.md) サンプルには、次の3つの手順を実行するのに役立つ3つのマクロが含まれています。、、 `DECLARE_DUAL_ERRORINFO` `DUAL_ERRORINFO_PART` および `IMPLEMENT_DUAL_ERRORINFO` すべてが mfcdual .h に含まれています)。

次の例では、をサポートするように定義されたクラスを実装して `ISupportErrorInfo` います。 `CAutoClickDoc` はオートメーションクラスの名前で、 `IID_IDualAClick` は OLE オートメーション error オブジェクトを介して報告されるエラーのソースであるインターフェイスの **IID** です。

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(
    REFIID iid)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return (iid == IID_IDualAClick) S_OK : S_FALSE;
}
```

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
