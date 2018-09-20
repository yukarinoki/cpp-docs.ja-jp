---
title: 'TN065: OLE オートメーション サーバー用デュアル インターフェイス サポート |Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.ole
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 837149397ec45ebd8b41808b170b9f5e25146d6a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387693"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このノートでは、OLE オートメーションを MFC ベースのサーバー アプリケーションにデュアル インターフェイス サポートを追加する方法について説明します。 [ACDUAL](../visual-cpp-samples.md)サンプルは、デュアル インターフェイス サポートとコード例では、この注は ACDUAL から取得されます。 DECLARE_DUAL_ERRORINFO、DUAL_ERRORINFO_PART、テクニカルなど、この注で説明されているマクロ ACDUAL サンプルの一部でありで説明することができます。H.

## <a name="dual-interfaces"></a>デュアル インターフェイス

OLE オートメーションでは、実装するために使用できますが、`IDispatch`インターフェイス、VTBL インターフェイス、または (両方が含まれます) をデュアル インターフェイスを公開されたすべての OLE オートメーション オブジェクトのデュアル インターフェイスを実装することを強くお勧めします。 デュアル インターフェイス経由で利点があります`IDispatch`-のみまたは VTBL 専用のインターフェイス。

- バインドをコンパイル時、VTBL インターフェイス、またはを介して実行時に実行できる`IDispatch`します。

- VTBL インターフェイスを使用する OLE オートメーション コント ローラーがパフォーマンスの向上を享受できます。

- 使用する既存の OLE オートメーション コント ローラー、`IDispatch`インターフェイスは引き続き機能します。

- VTBL インターフェイスは、C++ から呼び出す簡単です。

- デュアル インターフェイスは、Visual Basic のオブジェクトのサポートの機能と互換性のために必要です。

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget ベースのクラスへのデュアル インターフェイス サポートの追加

デュアル インターフェイスはから派生したカスタム インターフェイスにすぎません`IDispatch`します。 デュアル インターフェイス サポートを実装する最も簡単な方法を`CCmdTarget`-ベースのクラスは、通常のディスパッチ インターフェイス MFC と ClassWizard を使って、クラスをカスタム インターフェイスを後で追加の最初の実装にします。 カスタム インターフェイスの実装は、MFC に委任単にほとんどの場合、`IDispatch`実装します。

最初に、オブジェクトのデュアル インターフェイスを定義するサーバーの ODL ファイルを変更します。 デュアル インターフェイスを定義するには、代わりに、インターフェイス ステートメントを使用する必要があります、 `DISPINTERFACE` Visual C ウィザードで生成するステートメント。 既存の削除ではなく`DISPINTERFACE`ステートメントでは、新しいインターフェイス ステートメントを追加します。 保持することで、`DISPINTERFACE`フォーム、ClassWizard を使用して、オブジェクトにプロパティとメソッドを追加する続行できますが、インターフェイス ステートメントには、同等のプロパティとメソッドを追加する必要があります。

デュアル インターフェイス、インターフェイス ステートメントが必要、 *OLEAUTOMATION*と*デュアル*属性、およびインターフェイスから派生する必要があります`IDispatch`します。 使用することができます、 [GUIDGEN](../visual-cpp-samples.md)を作成するためのサンプルを**IID**デュアル インターフェイスの。

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

インターフェイス ステートメントである場合は、メソッドおよびプロパティのエントリの追加を開始します。 デュアル インターフェイスのメソッドとプロパティのアクセサー関数、デュアル インターフェイス内で返されるように、パラメーター リストを再配置する必要があります、 **HRESULT** 属性を持つパラメーターとして、戻り値を渡すと`[retval,out]`. プロパティが必要な読み書きの両方を追加するに注意してください (`propget`) と書き込み (`propput`) 同じ id を持つ関数にアクセスします。例えば:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

メソッドとプロパティを定義した後、coclass ステートメントで、インターフェイス ステートメントへの参照を追加する必要があります。 例えば:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

ODL ファイルを更新すると、MFC のインターフェイス マップ機構を使用して、オブジェクト クラスにデュアル インターフェイスの実装クラスを定義し、MFC ので、対応するエントリが作成`QueryInterface`メカニズム。 1 つのエントリを作成する必要があります、 `INTERFACE_PART` ODL のインターフェイスのステートメント内の各エントリとディスパッチ インターフェイスのエントリをブロックします。 各 ODL エントリ、 *propput*属性には、という名前の関数が必要があります`put_propertyname`します。 各エントリを*propget*属性には、という名前の関数が必要があります`get_propertyname`します。

デュアル インターフェイスの実装クラスを定義するには、追加、`DUAL_INTERFACE_PART`オブジェクト クラスの定義をブロックします。 例えば:

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

MFC にデュアル インターフェイスを接続する[QueryInterface](/windows/desktop/com/queryinterface--navigating-in-an-object)メカニズムでは、追加、`INTERFACE_PART`インターフェイス マップへのエントリ。

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

次に、インターフェイスの実装を入力する必要があります。 ほとんどの場合、ことができますに委任する既存の MFC`IDispatch`実装します。 例えば:

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

オブジェクトのメソッドおよびプロパティのアクセサー関数の実装を入力する必要があります。 メソッドとプロパティ関数は、ClassWizard を使って生成されたメソッドに一般的に委任できます。 ただし、変数に直接アクセスするプロパティを設定する場合は、変数に値を取得/格納するコードを記述する必要があります。 例えば:

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

## <a name="passing-dual-interface-pointers"></a>デュアル インターフェイス ポインターを渡す

呼び出す必要がある場合に特に簡単です。 デュアル インターフェイス ポインターを渡していない`CCmdTarget::FromIDispatch`します。 `FromIDispatch` MFC のでのみ機能`IDispatch`ポインター。 これを回避する 1 つの方法は、元のクエリに`IDispatch`ポインター セットは、MFC でし、必要な関数にそのポインターを渡します。 例えば:

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

デュアル インターフェイス メソッドを遡って、ポインターを渡す前に、MFC から変換する必要があります`IDispatch`にデュアル インターフェイス ポインターへのポインター。 例えば:

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

## <a name="registering-the-applications-type-library"></a>アプリケーションのタイプ ライブラリを登録します。

AppWizard では、システムに OLE オートメーション サーバー アプリケーションのタイプ ライブラリを登録するコードを生成しません。 タイプ ライブラリを登録するには、その他の方法はありますが、それが更新されるとき、OLE 型情報は、アプリケーションはスタンドアロンで実行されるたびに、タイプ ライブラリを登録、アプリケーションが便利です。

登録するには、アプリケーションが実行されるたびに、アプリケーションのタイプ ライブラリのスタンド アロンで。

- AFXCTL が含まれます。標準の時間には、ヘッダー ファイル、STDAFX が含まれています。定義にアクセスする、H、`AfxOleRegisterTypeLib`関数。

- アプリケーションの`InitInstance`関数への呼び出しを探し、`COleObjectFactory::UpdateRegistryAll`します。 この呼び出しへの呼び出しを追加`AfxOleRegisterTypeLib`を指定して、 **LIBID**タイプ ライブラリの名前と共に、タイプ ライブラリに対応します。

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

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>タイプ ライブラリの変更に対応するプロジェクトのビルド設定の変更

プロジェクトのビルド設定を変更するように、ヘッダー ファイルを含む**UUID**タイプ ライブラリを再構築されるたびにビルド定義が生成されます。

1. **ビルド** メニューのをクリックして**設定**、各構成ファイルの一覧から ODL ファイルを選択します。

2. をクリックして、 **OLE 型**] タブで [ファイル名を指定し、**出力ヘッダー** filename フィールド。 MkTypLib は既存のファイルを上書きするために、プロジェクトで使用されていないファイル名を使用します。 をクリックして**OK**を閉じる、 **Build Settings**  ダイアログ ボックス。

追加する、 **UUID** MkTypLib によって生成されたヘッダー ファイルをプロジェクトに定義します。

1. MkTypLib 生成は、ヘッダー ファイルで、標準のヘッダー ファイル、STDAFX が含まれています。H.

2. INITIIDS 新しいファイルを作成します。CPP、し、プロジェクトに追加します。 このファイルでは、OLE2 に含めた後で、ビルドによって生成されたヘッダー ファイルが含まれます。H および INITGUID します。H:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. **ビルド** メニューのをクリックして**設定**、し initiids とします。CPP ファイルの各構成の一覧から。

4. をクリックして、 **C++**  タブで、カテゴリ をクリックして**プリコンパイル済みヘッダー**を選択し、**プリコンパイル済みヘッダーを使用していない**ラジオ ボタンをクリックします。 閉じるには、ok をクリックして、 **Build Settings**  ダイアログ ボックス。

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>タイプ ライブラリに適切なオブジェクトのクラス名を指定します。

同梱されていない Visual C 正しくウィザードでは、実装クラスの名前を使用して、コクラスを OLE 作成可能なクラスのサーバーの ODL ファイルで指定します。 これは機能しますが、実装クラス名がない可能性がありますを使用するユーザー オブジェクトのクラス名にします。 正しい名前を指定するには、ODL ファイルを開き、各 coclass ステートメントを見つけて実装クラス名を正しいの外部の名前に置き換えます。

Coclass ステートメントが変更されたときに、変数の名前に注意して**CLSID**MkTypLib によって生成されたヘッダー ファイルでは適宜変更されます。 新しい変数名を使用するコードを更新する必要があります。

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>例外の処理とオートメーションのエラー インターフェイス

オートメーション オブジェクトのメソッドとプロパティのアクセサー関数には、例外がスローされます。 そのため、デュアル インターフェイスの実装でそれらを処理する必要があります、例外に関する情報を OLE オートメーション エラー処理インターフェイスでは、コント ローラーに渡すとする`IErrorInfo`します。 このインターフェイスを両方の詳細なコンテキスト エラー情報の提供`IDispatch`と VTBL インターフェイス。 エラー ハンドラーが使用可能なことは、実装することを示すために、`ISupportErrorInfo`インターフェイス。

エラー処理メカニズムを示すためには、標準のディスパッチのサポートを実装するために使用 ClassWizard で生成された関数が例外をスローすることを想定しています。 Mfc の`IDispatch::Invoke`通常これらの例外をキャッチしから返される EXCEPTINFO 構造体に変換して、`Invoke`呼び出します。 ただし、VTBL インターフェイスを使用する場合は、自分で例外をキャッチする責任が。 保護、デュアル インターフェイス メソッドの例です。

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

`CATCH_ALL_DUAL` 例外が発生したときに、適切なエラー コードを返す処理されます。 `CATCH_ALL_DUAL` OLE オートメーション エラー処理の情報を使用して MFC 例外に変換、`ICreateErrorInfo`インターフェイス。 (たとえば`CATCH_ALL_DUAL`マクロは、MFCDUAL ファイル。H、 [ACDUAL](../visual-cpp-samples.md)サンプル。 例外を処理するために呼び出す関数`DualHandleException`、MFCDUAL ファイルにします。CPP。)`CATCH_ALL_DUAL`発生した例外の種類に基づいて返されるエラー コードを決定します。

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - この場合、`HRESULT`は次のコードを使用して作成します。

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

     これを作成、`HRESULT`例外の原因となったインターフェイスを特定します。 エラー コードのオフセットはシステム定義との競合を回避するために 0x200`HRESULT`の標準の OLE インターフェイス。

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - この場合、`E_OUTOFMEMORY`が返されます。

- -この場合、その他の例外`E_UNEXPECTED`が返されます。

OLE オートメーションのエラー ハンドラーを使用しても実装することを示すために、`ISupportErrorInfo`インターフェイス。

最初に、コードを表示をサポートするオートメーション クラス定義に追加`ISupportErrorInfo`します。

関連付ける automation クラスのインターフェイス マップに第 2 に、コードを追加、`ISupportErrorInfo`実装クラスで MFC の`QueryInterface`メカニズム。 `INTERFACE_PART`ステートメントが定義されているクラスと一致する`ISupportErrorInfo`します。

最後に、サポートするために定義されているクラスを実装`ISupportErrorInfo`します。

(、 [ACDUAL](../visual-cpp-samples.md)サンプルには、これら 3 つの手順を実行する 3 つのマクロが含まれています`DECLARE_DUAL_ERRORINFO`、 `DUAL_ERRORINFO_PART`、および`IMPLEMENT_DUAL_ERRORINFO`ですべて含まれています。H.)

次の例では、サポートするために定義されているクラスを実装する`ISupportErrorInfo`します。 `CAutoClickDoc` オートメーション クラスの名前を指定し、`IID_IDualAClick`は、 **IID** OLE オートメーション エラー オブジェクトを通じて報告されたエラーのソースであるインターフェイスの。

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

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
