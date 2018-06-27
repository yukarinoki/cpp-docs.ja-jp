---
title: 'TN065: OLE オートメーション サーバー用デュアル インターフェイス サポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: b066ac483de127e0ce469cf8aaf24991ae5f6ef8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953039"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このノートでは、MFC ベースの OLE オートメーション サーバー アプリケーションにデュアル インターフェイス サポートを追加する方法について説明します。 [ACDUAL](../visual-cpp-samples.md)デュアル インターフェイス サポートのサンプルし、このコード例は、ACDUAL から取得します。 DECLARE_DUAL_ERRORINFO、DUAL_ERRORINFO_PART、およびテクニカルなどを説明するよう、マクロは、ACDUAL サンプルの一部であるしで説明することができます。H.  
  
## <a name="dual-interfaces"></a>デュアル インターフェイス  
 OLE オートメーションで実装することはできますが、`IDispatch`インターフェイス、VTBL インターフェイス、または、デュアル インターフェイス (両方が含まれます)、公開されたすべての OLE オートメーション オブジェクトには、デュアル インターフェイスを実装することを強くお勧めします。 デュアル インターフェイス経由で重要な利点がある`IDispatch`-のみまたは VTBL 専用のインターフェイス。  
  
-   バインドを行う、VTBL インターフェイスでは、コンパイル時に、またはを介して実行時に`IDispatch`です。  
  
-   VTBL インターフェイスを使用する OLE オートメーション コント ローラーは、パフォーマンスの向上を活用可能性があります。  
  
-   使用する既存の OLE オートメーション コント ローラー、`IDispatch`インターフェイスは引き続き機能します。  
  
-   VTBL インターフェイスは、C++ からを呼び出す簡単です。  
  
-   デュアル インターフェイスは、Visual Basic のオブジェクトのサポートの機能と互換性のため必要があります。  
  
## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget ベースのクラスへのデュアル インターフェイス サポートの追加  
 デュアル インターフェイスは、実際には、カスタムのインターフェイスから派生した`IDispatch`です。 デュアル インターフェイス サポートを実装する最も簡単な方法、 `CCmdTarget`-ベースのクラスが通常のディスパッチ インターフェイス MFC と ClassWizard を使って、クラスをカスタムのインターフェイスを後で追加の最初の実装です。 ほとんどの場合、カスタム インターフェイスの実装はバックアップにデリゲート MFC`IDispatch`実装します。  
  
 最初に、オブジェクトのデュアル インターフェイスを定義するようにサーバー用の ODL ファイルを変更します。 デュアル インターフェイスを定義するのには、代わりに、インターフェイス ステートメントを使用する必要があります、 `DISPINTERFACE` Visual C ウィザードで生成するステートメント。 既存の削除ではなく`DISPINTERFACE`ステートメントでは、新しいインターフェイス ステートメントを追加します。 保持することで、`DISPINTERFACE`フォーム、ClassWizard を使用して、オブジェクトにプロパティとメソッドを追加する続行できますが、インターフェイス ステートメントを同等のプロパティとメソッドを追加する必要があります。  
  
 デュアル インターフェイス用のインターフェイス ステートメント必要があります、 *OLEAUTOMATION*と*デュアル*属性、およびインターフェイスから派生しなければなりません`IDispatch`です。 使用することができます、 [GUIDGEN](../visual-cpp-samples.md)を作成するサンプル、 **IID**デュアル インターフェイスの。  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
    oleautomation, 
    dual 
]  
interface IDualAClick : IDispatch  
 {  
 };  
```  
  
 インプレース インターフェイス ステートメントがある場合、開始メソッドとプロパティのエントリを追加します。 デュアル インターフェイスのメソッドとデュアル インターフェイスのプロパティのアクセサー関数を返すように、パラメーター リストのレイアウトを変更する必要があります、 **HRESULT** の属性を持つパラメーターとして、戻り値を渡すと`[retval,out]`. プロパティの場合が必要な読み書きの両方を追加する (`propget`) および書き込み (`propput`) 同じ id を持つ関数にアクセスします。例えば:  
  
```  
[propput,
    id(1)] HRESULT text([in] BSTR newText);

[propget,
    id(1)] HRESULT text([out,
    retval] BSTR* retval);
```  
  
 メソッドとプロパティを定義したら、コクラス ステートメントで、インターフェイス ステートメントへの参照を追加する必要があります。 例えば:  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
    dispinterface IAClick;  
 [default] interface IDualAClick;  
};  
```  
  
 ODL ファイルを更新するは、MFC のインターフェイス マップ機構を使用してオブジェクトのクラス デュアル インターフェイスの実装クラスを定義し、MFC に対応するエントリが作成`QueryInterface`メカニズムです。 内の 1 つのエントリを作成する必要があります、`INTERFACE_PART`ディスパッチ インターフェイスのエントリに加え、ODL のインターフェイス ステートメント内の各エントリをブロックします。 各 ODL エントリを*propput*属性には、という名前の関数が必要があります`put_propertyname`です。 各エントリを*propget*属性には、という名前の関数が必要があります`get_propertyname`です。  
  
 デュアル インターフェイスの実装クラスを定義するのには、追加、`DUAL_INTERFACE_PART`オブジェクト クラスの定義をブロックします。 例えば:  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick,
    IDualAClick)  
    STDMETHOD(put_text)(THIS_ BSTR newText);

    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);

    STDMETHOD(put_x)(THIS_ short newX);

    STDMETHOD(get_x)(THIS_ short FAR* retval);

    STDMETHOD(put_y)(THIS_ short newY);

    STDMETHOD(get_y)(THIS_ short FAR* retval);

    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);

    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);

    STDMETHOD(RefreshWindow)(THIS);

 STDMETHOD(SetAllProps)(THIS_ short x,
    short y,
    BSTR text);

    STDMETHOD(ShowWindow)(THIS);

END_DUAL_INTERFACE_PART(DualAClick) 
```  
  
 MFC にデュアル インターフェイスを接続する[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230)機構を追加、`INTERFACE_PART`インターフェイス マップへのエントリ。  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc,
    CDocument)  
    INTERFACE_PART(CAutoClickDoc,
    DIID_IAClick,
    Dispatch)  
    INTERFACE_PART(CAutoClickDoc,
    IID_IDualAClick,
    DualAClick)  
END_INTERFACE_MAP()  
```  
  
 次に、インターフェイスの実装を入力する必要があります。 ほとんどの場合、ことができますを既存の MFC を委任する`IDispatch`実装します。 例えば:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalAddRef();

}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalRelease();

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfoCount(pctinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo,
    lcid,
    pptinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,  
    LCID lcid,
    DISPID FAR* rgdispid)   
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid,
    rgszNames,
    cNames,   
    lcid,
    rgdispid);

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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember,
    riid,
    lcid,  
    wFlags,
    pdispparams,
    pvarResult,  
    pexcepinfo,
    puArgErr);

}  
```  
  
 オブジェクトのメソッドとプロパティのアクセサー関数も実装する必要があります。 メソッドとプロパティ関数は、ClassWizard を使用して生成されたメソッドに一般的に委任できます。 ただし、変数に直接アクセスするプロパティを設定する場合は、変数に値を取得/格納するコードを記述する必要があります。 例えば:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Unicode BSTR to *// Ansi CString,
    if necessary...  
    pThis->m_str = newText;  
    return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Ansi CString to *// Unicode BSTR,
    if necessary...  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDisp;  
    lpDisp = pThis->GetPosition();
lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);

    return NOERROR;  
}  
```  
  
## <a name="registering-the-applications-type-library"></a>アプリケーションのタイプ ライブラリの登録  
 AppWizard では、システムで OLE オートメーション サーバー アプリケーションのタイプ ライブラリを登録するコードを生成しません。 タイプ ライブラリを登録する他の方法はありますが、アプリケーションの更新の OLE 型情報は、アプリケーションは、スタンドアロンで実行されるたびに、タイプ ライブラリを登録すると便利です。  
  
 登録するには、アプリケーションのタイプ ライブラリ、アプリケーションが実行されるたびにスタンド アロン。  
  
-   AFXCTL が含まれます。H、標準にはには、ヘッダー ファイル、STDAFX が含まれています。定義にアクセスする、H、`AfxOleRegisterTypeLib`関数。  
  
-   アプリケーションの`InitInstance`関数への呼び出しを探し、`COleObjectFactory::UpdateRegistryAll`です。 この呼び出しでは、次の呼び出しを追加して`AfxOleRegisterTypeLib`を指定して、 **LIBID**タイプ ライブラリの名前と共に、タイプ ライブラリに対応します。  
  
 '' */ことをお勧めはサーバー アプリケーションが起動すると、スタンドアロン/*//が破損した場合に、システム レジストリを更新します。  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

 COleObjectFactory::UpdateRegistryAll() です。*//DUAL_SUPPORT_START */、タイプ ライブラリが登録されているか、デュアル インターフェイスは動作しないかどうかを確認します。  
AfxOleRegisterTypeLib(AfxGetInstanceHandle()、LIBID_ACDual、_T("AutoClik.TLB")) です。*//DUAL_SUPPORT_END  
 ```  
  
## Modifying Project Build Settings to Accommodate Type Library Changes  
 To modify a project's build settings so that a header file containing **UUID** definitions is generated by MkTypLib whenever the type library is rebuilt:  
  
1.  On the **Build** menu, click **Settings**, and then select the ODL file from the file list for each configuration.  
  
2.  Click the **OLE Types** tab and specify a filename in the **Output header** filename field. Use a filename that is not already used by your project, because MkTypLib will overwrite any existing file. Click **OK** to close the **Build Settings** dialog box.  
  
 To add the **UUID** definitions from the MkTypLib-generated header file to your project:  
  
1.  Include the MkTypLib-generated header file in your standard includes header file, STDAFX.H.  
  
2.  Create a new file, INITIIDS.CPP, and add it to your project. In this file, include your MkTypLib-generated header file after including OLE2.H and INITGUID.H:  
  
 ```  
    initIIDs.c: デュアル インターフェイスの Iid を定義します。  
    プリコンパイル済みヘッダーとこれに構築する必要がありません。  
      #<a name="include-ole2h"></a>< ole2.h > が含まれます  
      #<a name="include-initguidh"></a>include <initguid.h>  
      #<a name="include-acdualh"></a>"acdual.h"を含める  
 ```  
  
3.  On the **Build** menu, click **Settings**, and then select INITIIDS.CPP from the file list for each configuration.  
  
4.  Click the **C++** tab, click category **Precompiled Headers**, and select the **Not using precompiled headers** radio button. Click OK to close the **Build Settings** dialog box.  
  
## Specifying the Correct Object Class Name in the Type Library  
 The wizards shipped with Visual C++ incorrectly use the implementation class name to specify the coclass in the server's ODL file for OLE-creatable classes. While this will work, the implementation class name is probably not the class name you want users of your object to use. To specify the correct name, open the ODL file, locate each coclass statement, and replace the implementation class name with the correct external name.  
  
 Note that when the coclass statement is changed, the variable names of **CLSID**s in the MkTypLib-generated header file will change accordingly. You will need to update your code to use the new variable names.  
  
## Handling Exceptions and the Automation Error Interfaces  
 Your automation object's methods and property accessor functions may throw exceptions. If so, you should handle them in your dual-interface implementation and pass information about the exception back to the controller through the OLE Automation error-handling interface, `IErrorInfo`. This interface provides for detailed, contextual error information through both `IDispatch` and VTBL interfaces. To indicate that an error handler is available, you should implement the `ISupportErrorInfo` interface.  
  
 To illustrate the error-handling mechanism, assume that the ClassWizard-generated functions used to implement the standard dispatch support throw exceptions. MFC's implementation of `IDispatch::Invoke` typically catches these exceptions and converts them into an EXCEPTINFO structure that is returned through the `Invoke` call. However, when VTBL interface is used, you are responsible for catching the exceptions yourself. As an example of protecting your dual-interface methods:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE (CAutoClickDoc、DualAClick)  
    TRY_DUAL(IID_IDualAClick) {*/MFC が自動的に変換する Unicode BSTR から/*//Ansi CString、必要に応じて.  
    pThis m_str]-> [= 新しいテキストを入力します。  
    NOERROR; を返す  
 }  
    発生時}  
```  
  
 `CATCH_ALL_DUAL` takes care of returning the correct error code when an exception occurs. `CATCH_ALL_DUAL` converts an MFC exception into OLE Automation error-handling information using the `ICreateErrorInfo` interface. (An example `CATCH_ALL_DUAL` macro is in the file MFCDUAL.H in the [ACDUAL](../visual-cpp-samples.md) sample. The function it calls to handle exceptions, `DualHandleException`, is in the file MFCDUAL.CPP.) `CATCH_ALL_DUAL` determines the error code to return based on the type of exception that occurred:  
  
- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - In this case, `HRESULT` is constructed using the following code:  
  
 ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR,
    FACILITY_ITF,   
 (e -> m_wCode + 0x200)) です。

 ```  
  
     This creates an `HRESULT` specific to the interface that caused the exception. The error code is offset by 0x200 to avoid any conflicts with system-defined `HRESULT`s for standard OLE interfaces.  
  
- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - In this case, `E_OUTOFMEMORY` is returned.  
  
-   Any other exception - In this case, `E_UNEXPECTED` is returned.  
  
 To indicate that the OLE Automation error handler is used, you should also implement the `ISupportErrorInfo` interface.  
  
 First, add code to your automation class definition to show it supports `ISupportErrorInfo`.  
  
 Second, add code to your automation class's interface map to associate the `ISupportErrorInfo` implementation class with MFC's `QueryInterface` mechanism. The `INTERFACE_PART` statement matches the class defined for `ISupportErrorInfo`.  
  
 Finally, implement the class defined to support `ISupportErrorInfo`.  
  
 (The [ACDUAL](../visual-cpp-samples.md) sample contains three macros to help do these three steps, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, and `IMPLEMENT_DUAL_ERRORINFO`, all contained in MFCDUAL.H.)  
  
 The following example implements a class defined to support `ISupportErrorInfo`. `CAutoClickDoc` is the name of your automation class and `IID_IDualAClick` is the **IID** for the interface that is the source of errors reported through the OLE Automation error object:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
    METHOD_PROLOGUE (CAutoClickDoc、SupportErrorInfo)   
    戻り値の pThis ExternalAddRef();]-> [します。

}   
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
    METHOD_PROLOGUE (CAutoClickDoc、SupportErrorInfo)   
    戻り値の pThis ExternalRelease();]-> [します。

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface (REFIID iid、LPVOID * ppvObj)   
{   
    METHOD_PROLOGUE (CAutoClickDoc、SupportErrorInfo)   
    戻り値の pThis は ExternalQueryInterface (& iid、ppvObj); -> します。

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo (REFIID iid)   
{   
    METHOD_PROLOGUE (CAutoClickDoc、SupportErrorInfo)   
    return (iid == IID_IDualAClick) S_OK : S_FALSE;   
}  
```  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

