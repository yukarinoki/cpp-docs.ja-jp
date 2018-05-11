---
title: 属性のプログラミングの FAQ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributed programming
- attributes [C++], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35b57c8813778cf0bbf8efbfcbee8466074b87f0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="attribute-programming-faq"></a>属性プログラミングの FAQ
このトピックは、以下のよく寄せられる質問に回答します。  
  
-   [HRESULT は何ですか。](#vcconattributeprogrammmingfaqanchor1)  
  
-   [属性のパラメーター名の指定がある場合](#vcconattributeprogrammmingfaqanchor2)  
  
-   [属性ブロックでコメントを使用できますか。](#vcconattributeprogrammmingfaqanchor3)  
  
-   [継承と属性が対話する方法](#vcconattributeprogrammmingfaqanchor4)  
  
-   [属性なしの ATL プロジェクトでの属性を使用する方法は?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [属性付きプロジェクトに .idl ファイルを使用する方法は?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [属性によって挿入されたコードを変更できますか。](#vcconattributeprogrammmingfaqanchor7)  
  
-   [転送を宣言する方法、属性付きインターフェイスしますか。](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [属性を使用するクラスから派生したクラスで属性を使用することができますか。](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> HRESULT は何ですか。  
 `HRESULT`は多くの場合、使用される戻り値として属性と ATL で一般に単純なデータ型です。 次の表では、さまざまな値について説明します。 ヘッダー ファイル winerror.h には、多くの値が含まれています。  
  
|名前|説明|[値]|  
|----------|-----------------|-----------|  
|S_OK|処理は成功しました|0x00000000|  
|E_UNEXPECTED|予期しないエラー|0x8000FFFF|  
|E_NOTIMPL|実装されていません|0x80004001|  
|E_OUTOFMEMORY|必要なメモリを割り当てられませんでした。|0x8007000E|  
|E_INVALIDARG|1 つまたは複数の引数が有効ではありません。|0x80070057|  
|E_NOINTERFACE|インターフェイスがサポートされています。|0x80004002|  
|E_POINTER|無効なポインター|0x80004003|  
|E_HANDLE|ハンドルが無効です。|0x80070006|  
|E_ABORT|操作は中止されました|0x80004004|  
|E_FAIL|特定できないエラー|0x80004005|  
|E_ACCESSDENIED|アクセス拒否エラー|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> 属性のパラメーター名の指定がある場合  
 ほとんどの場合、属性が 1 つのパラメーターを持つ場合、そのパラメーターは名前です。 コード内の属性を挿入するときに、この名前は必要ありません。 次の使用法など、[集約可能](../windows/aggregatable.md)属性。  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 まったく同じであるとします。  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 ただし、次の属性には、単一の名前のないパラメーターがあります。  
  
||||  
|-|-|-|  
|[call_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[entry](../windows/entry.md)|[first_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[ID](../windows/id.md)|  
|[iid_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[include](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last_is](../windows/last-is.md)|  
|[length_is](../windows/length-is.md)|[max_is](../windows/max-is.md)|[no_injected_text](../windows/no-injected-text.md)|  
|[pointer_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size_is](../windows/size-is.md)|[ソース](../windows/source-cpp.md)|[switch_is](../windows/switch-is.md)|  
|[switch_type](../windows/switch-type.md)|[transmit_as](../windows/transmit-as.md)|[wire_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> 属性ブロックでコメントを使用できますか。  
 属性ブロック内で単一行および複数行の両方のコメントを使用することができます。 ただし、属性にパラメーターを保持しているかっこで囲まれたコメントのいずれかのスタイルを使用することはできません。  
  
 次は使用できます。  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 次は許可されていません。  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> 継承と属性が対話する方法  
 付きか、他のクラスから属性と属性の両方のクラスを継承することができます。 属性付きクラスから派生した結果は、属性プロバイダーはそのコードを変換した後、そのクラスから派生する場合と同じです。 C++ の継承を使用してクラスを派生する属性は送信されません。 のみ、属性プロバイダーは、その属性の付近のコードを変換します。  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> 属性なしの ATL プロジェクトでの属性を使用する方法は?  
 .Idl ファイルを持つ属性なしの ATL プロジェクトがあります、属性付きオブジェクトの追加を開始することがあります。 この例では、クラスの追加ウィザードを使用して、コードを提供します。  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> 属性付きプロジェクトに .idl ファイルを使用する方法は?  
 .Idl ファイル属性 ATL プロジェクトで使用するがあります。 この場合、使用すると、 [importidl](../windows/importidl.md)属性、.idl ファイルと .h ファイルのコンパイル (を参照してください、 [midl プロパティ ページ](../ide/midl-property-pages.md)プロジェクトのプロパティ ページ ダイアログ ボックスで)、.h ファイルをプロジェクトに含める.  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> 属性によって挿入されたコードを変更できますか。  
 いくつかの属性は、プロジェクトにコードを挿入します。 使用して挿入されたコードを確認できます、 [/Fx](../build/reference/fx-merge-injected-code.md)コンパイラ オプション。 挿入されたファイルからコードをコピーして、ソース コードに貼り付けることもできます。 これにより、属性の動作を変更することができます。 ただしもコードの他の部分を変更する必要があります。  
  
 次の例では、ソース コード ファイルに挿入されたコードをコピーの結果を示します。  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
]  
  
class ATL_NO_VTABLE CTestTest : public ITestTest,  
// the following base classes support added injected code  
public IConnectionPointContainerImpl<CTestTest>,  
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>  
{  
public:  
   CTestTest() {  
   }  
   // this line would be commented out from original file  
   // __event __interface _ITestTestEvents;  
   DECLARE_PROTECT_FINAL_CONSTRUCT()  
   HRESULT FinalConstruct() {  
      return S_OK;  
   }  
  
void FinalRelease() {}  
  
public:  
   CComBSTR m_value;  
   STDMETHOD(DoTest)(BSTR str) {  
      VARIANT_BOOL bCancel = FALSE;  
      BeforeChange(str,&bCancel);  
      if (bCancel) {  
          return Error("Error : Someone don't want us to change the value");  
      }  
  
     m_value =str;  
     return S_OK;  
    }  
// the following was copied in from the injected code.  
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {  
   HRESULT hr = S_OK;  
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;  
   VARIANT rgvars[2];  
   Lock();  
   IUnknown** pp = p->m_vec.begin();  
   Unlock();  
   while (pp < p->m_vec.end()) {  
      if (*pp != NULL) {  
         IDispatch* pDispatch = (IDispatch*) *pp;  
         ::VariantInit(&rgvars[1]);  
         rgvars[1].vt = VT_BSTR;  
         V_BSTR(&rgvars[1])= (BSTR) i1;  
         ::VariantInit(&rgvars[0]);  
         rgvars[0].vt = (VT_BOOL | VT_BYREF);  
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;  
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };  
         VARIANT ret_val;  
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);  
         if (FAILED(hr))  
            break;  
      }  
      pp++;  
   }  
   return hr;  
}  
  
BEGIN_CONNECTION_POINT_MAP(CTestTest)  
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))  
END_CONNECTION_POINT_MAP()  
// end added code section  
  
// _ITestCtrlEvents Methods  
public:  
};  
  
int main() {}  
```  
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> 転送を宣言する方法、属性付きインターフェイスしますか。  
 属性付きインターフェイスの事前宣言を作成しようとする場合は、実際のインターフェイスの宣言に適用される事前宣言に同じ属性を適用する必要があります。 適用する必要も、[エクスポート](../windows/export.md)属性を事前宣言します。  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> 属性を使用するクラスから派生したクラスで属性を使用することができますか。  
 いいえ、属性を使用するクラスから派生したクラスで属性の使用はサポートされていません。  
  
## <a name="see-also"></a>関連項目  
 [概念](../windows/attributed-programming-concepts.md)