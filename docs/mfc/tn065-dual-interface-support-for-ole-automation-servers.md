---
title: 'TN065: OLE オートメーション サーバー用デュアル インターフェイス サポート |Microsoft ドキュメント'
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
ms.openlocfilehash: e30be46aeab92f63f1b4cba593cda52bf9aeef9a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122184"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このノートでは、MFC ベースの OLE オートメーション サーバー アプリケーションにデュアル インターフェイス サポートを追加する方法について説明します。 [ACDUAL](../visual-cpp-samples.md)デュアル インターフェイス サポートのサンプルし、このコード例は、ACDUAL から取得します。 DECLARE_DUAL_ERRORINFO、DUAL_ERRORINFO_PART、およびテクニカルなどを説明するよう、マクロは、ACDUAL サンプルの一部であるしで説明することができます。H.

## <a name="dual-interfaces"></a>デュアル インターフェイス

OLE オートメーションで実装することはできますが、`IDispatch`インターフェイス、VTBL インターフェイス、または、デュアル インターフェイス (両方が含まれます)、公開されたすべての OLE オートメーション オブジェクトには、デュアル インターフェイスを実装することを強くお勧めします。 デュアル インターフェイス経由で重要な利点がある`IDispatch`-のみまたは VTBL 専用のインターフェイス。

- バインドを行う、VTBL インターフェイスでは、コンパイル時に、またはを介して実行時に`IDispatch`です。

- VTBL インターフェイスを使用する OLE オートメーション コント ローラーは、パフォーマンスの向上を活用可能性があります。

- 使用する既存の OLE オートメーション コント ローラー、`IDispatch`インターフェイスは引き続き機能します。

- VTBL インターフェイスは、C++ からを呼び出す簡単です。

- デュアル インターフェイスは、Visual Basic のオブジェクトのサポートの機能と互換性のため必要があります。

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget ベースのクラスへのデュアル インターフェイス サポートの追加

デュアル インターフェイスは、実際には、カスタムのインターフェイスから派生した`IDispatch`です。 デュアル インターフェイス サポートを実装する最も簡単な方法、 `CCmdTarget`-ベースのクラスが通常のディスパッチ インターフェイス MFC と ClassWizard を使って、クラスをカスタムのインターフェイスを後で追加の最初の実装です。 ほとんどの場合、カスタム インターフェイスの実装はバックアップにデリゲート MFC`IDispatch`実装します。

最初に、オブジェクトのデュアル インターフェイスを定義するようにサーバー用の ODL ファイルを変更します。 デュアル インターフェイスを定義するのには、代わりに、インターフェイス ステートメントを使用する必要があります、 `DISPINTERFACE` Visual C ウィザードで生成するステートメント。 既存の削除ではなく`DISPINTERFACE`ステートメントでは、新しいインターフェイス ステートメントを追加します。 保持することで、`DISPINTERFACE`フォーム、ClassWizard を使用して、オブジェクトにプロパティとメソッドを追加する続行できますが、インターフェイス ステートメントを同等のプロパティとメソッドを追加する必要があります。

デュアル インターフェイス用のインターフェイス ステートメント必要があります、 *OLEAUTOMATION*と*デュアル*属性、およびインターフェイスから派生しなければなりません`IDispatch`です。 使用することができます、 [GUIDGEN](../visual-cpp-samples.md)を作成するサンプル、 **IID**デュアル インターフェイスの。

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

インプレース インターフェイス ステートメントがある場合、開始メソッドとプロパティのエントリを追加します。 デュアル インターフェイスのメソッドとデュアル インターフェイスのプロパティのアクセサー関数を返すように、パラメーター リストのレイアウトを変更する必要があります、 **HRESULT** の属性を持つパラメーターとして、戻り値を渡すと`[retval,out]`. プロパティの場合が必要な読み書きの両方を追加する (`propget`) および書き込み (`propput`) 同じ id を持つ関数にアクセスします。例えば:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

メソッドとプロパティを定義したら、コクラス ステートメントで、インターフェイス ステートメントへの参照を追加する必要があります。 例えば:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

ODL ファイルを更新するは、MFC のインターフェイス マップ機構を使用してオブジェクトのクラス デュアル インターフェイスの実装クラスを定義し、MFC に対応するエントリが作成`QueryInterface`メカニズムです。 内の 1 つのエントリを作成する必要があります、`INTERFACE_PART`ディスパッチ インターフェイスのエントリに加え、ODL のインターフェイス ステートメント内の各エントリをブロックします。 各 ODL エントリを*propput*属性には、という名前の関数が必要があります`put_propertyname`です。 各エントリを*propget*属性には、という名前の関数が必要があります`get_propertyname`です。

デュアル インターフェイスの実装クラスを定義するのには、追加、`DUAL_INTERFACE_PART`オブジェクト クラスの定義をブロックします。 例えば:

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

MFC にデュアル インターフェイスを接続する[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230)機構を追加、`INTERFACE_PART`インターフェイス マップへのエントリ。

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

次に、インターフェイスの実装を入力する必要があります。 ほとんどの場合、ことができますを既存の MFC を委任する`IDispatch`実装します。 例えば:

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

オブジェクトのメソッドとプロパティのアクセサー関数も実装する必要があります。 メソッドとプロパティ関数は、ClassWizard を使用して生成されたメソッドに一般的に委任できます。 ただし、変数に直接アクセスするプロパティを設定する場合は、変数に値を取得/格納するコードを記述する必要があります。 例えば:

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

呼び出す必要がある場合に特に簡単です。 されていない、デュアル インターフェイス ポインターを渡す`CCmdTarget::FromIDispatch`です。 `FromIDispatch` MFC のでのみ機能`IDispatch`ポインター。 これを回避する方法の 1 つは、元のクエリに`IDispatch`ポインター セットは、MFC でし、必要な関数にそのポインターを渡します。 例えば:

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

デュアル インターフェイス メソッドを介して返さへのポインターを渡す前に、MFC から変換する必要があります`IDispatch`デュアル インターフェイス ポインターへのポインター。 例えば:

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

## <a name="registering-the-applications-type-library"></a>アプリケーションのタイプ ライブラリの登録

AppWizard では、システムで OLE オートメーション サーバー アプリケーションのタイプ ライブラリを登録するコードを生成しません。 タイプ ライブラリを登録する他の方法はありますが、アプリケーションの更新の OLE 型情報は、アプリケーションは、スタンドアロンで実行されるたびに、タイプ ライブラリを登録すると便利です。

登録するには、アプリケーションのタイプ ライブラリ、アプリケーションが実行されるたびにスタンド アロン。

- AFXCTL が含まれます。H、標準にはには、ヘッダー ファイル、STDAFX が含まれています。定義にアクセスする、H、`AfxOleRegisterTypeLib`関数。

- アプリケーションの`InitInstance`関数への呼び出しを探し、`COleObjectFactory::UpdateRegistryAll`です。 この呼び出しでは、次の呼び出しを追加して`AfxOleRegisterTypeLib`を指定して、 **LIBID**タイプ ライブラリの名前と共に、タイプ ライブラリに対応します。

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

プロジェクトのビルド設定を変更するように、ヘッダーを含んでいるファイル**UUID**定義が MkTypLib によって生成されるタイプ ライブラリが再構築されるたびに。

1. **ビルド** メニューのをクリックして**設定**、し ODL ファイルをそれぞれの構成ファイルの一覧から選択します。

2. クリックして、 **OLE タイプ**タブおよび ファイル名を指定、**出力ヘッダー** filename フィールドです。 MkTypLib は既存のファイルを上書きするために、プロジェクトで既に使用されていないファイル名を使用します。 をクリックして**OK**を閉じる、**ビルド設定** ダイアログ ボックス。

追加する、 **UUID** MkTypLib によって生成されたヘッダー ファイルからプロジェクトに定義します。

1. MkTypLib で生成されたを含む、標準のヘッダー ファイルには、ヘッダー ファイル、STDAFX が含まれています。H.

2. INITIIDS、新しいファイルを作成します。CPP、し、プロジェクトに追加します。 このファイルでは、OLE2 を含めた後、MkTypLib によって生成されたヘッダー ファイルを含めます。H と INITGUID です。H:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. **ビルド** メニューのをクリックして**設定**、し initiids とします。それぞれの構成ファイルの一覧から CPP です。

4. クリックして、 **C++**  タブで、カテゴリ をクリックして**プリコンパイル済みヘッダー**を選択し、**プリコンパイル済みヘッダーを使用していない**ラジオ ボタンをクリックします。 閉じるには、ok をクリックして、 **Build Settings**  ダイアログ ボックス。

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>タイプ ライブラリで適切なオブジェクトのクラス名を指定します。

付属していない Visual C 正しくウィザードでは、ファイルを指定する、コクラス、サーバーの ODL OLE 作成可能なクラスの実装のクラス名を使用します。 この動作は、実装クラス名はこのオブジェクトのユーザーは、使用するクラス名ではありません。 正しい名前を指定するには、ODL ファイルを開き、各コクラス ステートメントを見つけて実装クラス名を正しいの外部名に置き換えます。

なお、コクラス ステートメントが変更されたときに、変数名の**CLSID**MkTypLib によって生成されたヘッダー ファイルでは、それに応じて変更されます。 新しい変数名を使用するコードを更新する必要があります。

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>例外の処理とオートメーションのエラー インターフェイス

オートメーション オブジェクトのメソッドとプロパティのアクセサー関数には、例外がスローされます。 例外に関する情報を OLE オートメーションのエラー処理インターフェイス、コント ローラーに渡すし、デュアル インターフェイスの実装でそれらを処理する必要がありますので、`IErrorInfo`です。 このインターフェイスの両方を通じて、コンテキストの詳細なエラー情報提供`IDispatch`と VTBL インターフェイスです。 エラー ハンドラーが使用可能な実装する必要があることを示すために、`ISupportErrorInfo`インターフェイスです。

エラー処理メカニズムを示すためには、標準のディスパッチのサポートを実装するために使用 ClassWizard で生成される関数が例外をスローすることを想定しています。 Mfc の`IDispatch::Invoke`通常これらの例外をキャッチしから返される EXCEPTINFO 構造に変換して、`Invoke`呼び出します。 ただし、VTBL インターフェイスを使用する場合は、自分で例外をキャッチする必要があります。 デュアル インターフェイス メソッドを保護するための例です。

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

`CATCH_ALL_DUAL` 例外が発生したときに、正しいエラー コードを返す処理されます。 `CATCH_ALL_DUAL` OLE オートメーション エラー処理を使用して情報に MFC 例外を変換、`ICreateErrorInfo`インターフェイスです。 (たとえば`CATCH_ALL_DUAL`マクロは、ファイル MFCDUAL です。H、 [ACDUAL](../visual-cpp-samples.md)サンプルです。 例外を処理するために呼び出す関数`DualHandleException`、MFCDUAL ファイルにします。CPP。)`CATCH_ALL_DUAL`発生した例外の種類に基づいて返されるエラー コードを決定します。

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - この場合、`HRESULT`次のコードを使用して作成されます。

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

     これを作成、`HRESULT`例外の原因となったインターフェイスに固有です。 エラー コードはシステム定義と競合を回避する 0x200 オフセット`HRESULT`秒であり、標準の OLE インターフェイスです。

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - この場合、`E_OUTOFMEMORY`が返されます。

- ここでは、その他の例外`E_UNEXPECTED`が返されます。

OLE オートメーション エラー ハンドラーを使用して、実装することも必要がありますのことを示すために、`ISupportErrorInfo`インターフェイスです。

オートメーション クラス定義をサポートしていることを表示するコードを最初に、追加`ISupportErrorInfo`です。

次に、コードに関連付けるには、オートメーション クラスのインターフェイス マップを追加、`ISupportErrorInfo`実装クラスで MFC の`QueryInterface`メカニズムです。 `INTERFACE_PART`ステートメントに対して定義されているクラスに一致`ISupportErrorInfo`です。

最後に、サポートするために定義されているクラスを実装`ISupportErrorInfo`です。

(、 [ACDUAL](../visual-cpp-samples.md)サンプルには、これら 3 つの手順を行うための 3 つのマクロが含まれています`DECLARE_DUAL_ERRORINFO`、 `DUAL_ERRORINFO_PART`、および`IMPLEMENT_DUAL_ERRORINFO`で含まれているすべて、します。H.)

次の例は、サポートするために定義されたクラスを実装`ISupportErrorInfo`です。 `CAutoClickDoc` オートメーション クラスの名前を指定し、`IID_IDualAClick`は、 **IID** OLE オートメーション エラー オブジェクトを通じて報告されたエラーの原因となったインターフェイスの。

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

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)  
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)  
