---
title: 属性プログラミングの FAQ
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: 4191704da2fdac849ac1ce97692c2421ba7cda41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168384"
---
# <a name="attribute-programming-faq"></a>属性プログラミングの FAQ

このトピックでは、次のよく寄せられる質問に回答します。

- [HRESULT とは何ですか。](#vcconattributeprogrammmingfaqanchor1)

- [属性のパラメーター名を指定する必要があるのはどのような場合ですか。](#vcconattributeprogrammmingfaqanchor2)

- [属性ブロックでコメントを使用することはできますか。](#vcconattributeprogrammmingfaqanchor3)

- [属性と継承を連携させるにはどうすればよいですか。](#vcconattributeprogrammmingfaqanchor4)

- [属性なし ATL プロジェクトで属性を使用するにはどうすればよいですか。](#vcconattributeprogrammmingfaqanchor5)

- [属性付きのプロジェクトで .idl ファイルを使用するにはどうすればよいですか。](#vcconattributeprogrammmingfaqanchor6)

- [属性によって挿入されたコードを変更できますか。](#vcconattributeprogrammmingfaqanchor7)

- [属性付きインターフェイスを事前に宣言するにはどうすればよいですか。](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [属性も使用するクラスから派生したクラスで属性を使用できますか。](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

##  <a name="what-is-an-hresult"></a><a name="vcconattributeprogrammmingfaqanchor1"></a>HRESULT とは何ですか。

HRESULT は、属性と ATL によって一般的に戻り値として使用されることが多い単純なデータ型です。 次の表では、さまざまな値について説明します。 ヘッダーファイル winerror.h には、より多くの値が含まれています。

|Name|説明|値|
|----------|-----------------|-----------|
|S_OK|操作に成功しました|0x00000000|
|E_UNEXPECTED|予期しないエラー|0x8000FFFF|
|E_NOTIMPL|実装されていません|0x80004001|
|E_OUTOFMEMORY|必要なメモリを割り当てられませんでした|0x8007000E|
|E_INVALIDARG|1つ以上の引数が無効です|0x80070057|
|E_NOINTERFACE|そのようなインターフェイスはサポートされていません。|0x80004002|
|E_POINTER|無効なポインター|0x80004003|
|E_HANDLE|無効なハンドル|0x80070006|
|E_ABORT|操作が中止されました|0x80004004|
|E_FAIL|不特定のエラー|0x80004005|
|E_ACCESSDENIED|一般アクセス拒否エラー|0x80070005|

##  <a name="when-do-i-have-to-specify-the-parameter-name-for-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor2"></a>属性のパラメーター名を指定する必要があるのはどのような場合ですか。

ほとんどの場合、属性に1つのパラメーターがある場合、そのパラメーターにはという名前が付けられます。 この名前は、コードに属性を挿入するときには必要ありません。 次に、[集計](aggregatable.md)可能な属性の使用例を示します。

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

は、次の場合とまったく同じです。

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

ただし、次の属性には、名前のない単一のパラメーターがあります。

||||
|-|-|-|
|[call_as](call-as.md)|[case](case-cpp.md)|[cpp_quote](cpp-quote.md)|
|[既定値](default-cpp.md)|[defaultvalue](defaultvalue.md)|[defaultvtable](defaultvtable.md)|
|[emitidl](emitidl.md)|[entry](entry.md)|[first_is](first-is.md)|
|[helpcontext](helpcontext.md)|[helpfile](helpfile.md)|[helpstring](helpstring.md)|
|[helpstringcontext](helpstringcontext.md)|[helpstringdll](helpstringdll.md)|[id](id.md)|
|[iid_is](iid-is.md)|[import](import.md)|[importlib](importlib.md)|
|[include](include-cpp.md)|[includelib](includelib-cpp.md)|[last_is](last-is.md)|
|[length_is](length-is.md)|[max_is](max-is.md)|[no_injected_text](no-injected-text.md)|
|[pointer_default](pointer-default.md)|[pragma](pragma.md)|[restricted](restricted.md)|
|[size_is](size-is.md)|[source](source-cpp.md)|[switch_is](switch-is.md)|
|[switch_type](switch-type.md)|[transmit_as](transmit-as.md)|[wire_marshal](wire-marshal.md)|

##  <a name="can-i-use-comments-in-an-attribute-block"></a><a name="vcconattributeprogrammmingfaqanchor3"></a>属性ブロックでコメントを使用することはできますか。

1行のコメントと複数行のコメントは、属性ブロック内で使用できます。 ただし、属性のパラメーターを保持しているかっこ内では、どちらのスタイルのコメントも使用できません。

次のものを使用できます。

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

次は許可されていません。

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

##  <a name="how-do-attributes-interact-with-inheritance"></a><a name="vcconattributeprogrammmingfaqanchor4"></a>属性と継承を連携させるにはどうすればよいですか。

属性付きクラスと unattributed クラスの両方を他のクラスから継承できますが、それ自体は属性を持つことができます。 属性付きクラスからの派生の結果は、属性プロバイダーがそのコードを変換した後に、そのクラスから派生したものと同じです。 継承によってC++属性が派生クラスに送信されることはありません。 属性プロバイダーは、属性の近くのコードのみを変換します。

##  <a name="how-can-i-use-attributes-in-a-nonattributed-atl-project"></a><a name="vcconattributeprogrammmingfaqanchor5"></a>属性なし ATL プロジェクトで属性を使用するにはどうすればよいですか。

.Idl ファイルがある、属性なしの ATL プロジェクトがある場合、属性付きオブジェクトの追加を開始することができます。 この場合は、クラスの**追加ウィザード**を使用してコードを指定します。

##  <a name="how-can-i-use-an-idl-file-in-an-attributed-project"></a><a name="vcconattributeprogrammmingfaqanchor6"></a>属性付きのプロジェクトで .idl ファイルを使用するにはどうすればよいですか。

ATL 属性プロジェクトで使用する .idl ファイルがある可能性があります。 この場合は、次のように、使用することによって、取り込む[tidl](importidl.md)属性を使用して .idl ファイルをコンパイルします (プロジェクトの **[プロパティページ]** ダイアログボックスの [ [MIDL] プロパティページ](../../build/reference/midl-property-pages.md)を参照してください)。次に、プロジェクトに .h ファイルを含めます。

##  <a name="can-i-modify-code-that-is-injected-by-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor7"></a>属性によって挿入されたコードを変更できますか。

一部の属性では、プロジェクトにコードを挿入します。 [/Fx](../../build/reference/fx-merge-injected-code.md)コンパイラオプションを使用して、挿入されたコードを確認できます。 挿入されたファイルからコードをコピーして、ソースコードに貼り付けることもできます。 これにより、属性の動作を変更できます。 ただし、コードの他の部分も変更する必要がある場合があります。

次の例は、挿入されたコードをソースコードファイルにコピーした結果を示しています。

```cpp
// attr_injected.cpp
// compile with: comsupp.lib
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name="MyLibrary") ];

// ITestTest
[
   object, uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"), dual, helpstring("ITestTest Interface"), pointer_default(unique)
]

__interface ITestTest : IDispatch {
   [id(1), helpstring("method DoTest")]
   HRESULT DoTest([in] BSTR str);
};

// _ITestTestEvents
[
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"), dispinterface, helpstring("_ITestTestEvents Interface")
]

__interface _ITestTestEvents {
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);
};

// CTestTest
[
   coclass, threading(apartment), vi_progid("TestATL1.TestTest"), progid("TestATL1.TestTest.1"), version(1.0), uuid("D9632007-14FA-4679-9E1C-28C9A949E784"), // this line would be commented out from original file
   // event_source("com"), // this line would be added to support injected code
   source(_ITestTestEvents), helpstring("TestTest Class")
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

##  <a name="how-can-i-forward-declare-an-attributed-interface"></a><a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a>属性付きインターフェイスを事前に宣言するにはどうすればよいですか。

属性付きインターフェイスの事前宣言を行う場合は、実際のインターフェイス宣言に適用する事前宣言に同じ属性を適用する必要があります。 [Export](export.md)属性も事前宣言に適用する必要があります。

##  <a name="can-i-use-attributes-on-a-class-derived-from-a-class-that-also-uses-attributes"></a><a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a>属性も使用するクラスから派生したクラスで属性を使用できますか。

いいえ。属性を使用するクラスから派生したクラスで属性を使用することはサポートされていません。

## <a name="see-also"></a>参照

[COM および .NET の C++ の属性](cpp-attributes-com-net.md)
