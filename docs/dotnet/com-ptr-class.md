---
title: com::ptr Class
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: e494285f33cf282d7b7515aac374ec86ef3036b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372486"
---
# <a name="comptr-class"></a>com::ptr Class

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパー。  ラッパーは、COM オブジェクトの有効期間管理も自動化し、デストラクターが呼び出されたときに、オブジェクト上のすべての所有参照を解放します。 [CComPtr クラス](../atl/reference/ccomptr-class.md)に類似しています。

## <a name="syntax"></a>構文

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>パラメーター

*_interface_type*<br/>
COM インターフェイス。

## <a name="remarks"></a>解説

A`com::ptr`は、さまざまな COM タスクを簡略化し、有効期間管理を自動化するために、ローカル関数変数としても使用できます。

関数`com::ptr`パラメータとして直接使用することはできません。代わりに[、追跡参照演算子](../extensions/tracking-reference-operator-cpp-component-extensions.md)または[オブジェクトへのハンドル演算子 (^) を](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)使用します。

関数`com::ptr`から直接返すことはできません。代わりにハンドルを使用してください。

## <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。  クラスのパブリック メソッドを呼び出すと、含まれている`IXMLDOMDocument`オブジェクトが呼び出されます。  このサンプルでは、XML ドキュメントのインスタンスを作成し、その XML を単純な XML で満たし、解析されたドキュメント ツリー内のノードを簡単に操作して XML をコンソールに出力します。

```cpp
// comptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into the document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // simplified function to write just the first xml node to the console
   void WriteXml() {
      IXMLDOMNode* pNode = NULL;

      try {
         // the first child of the document is the first real xml node
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            WriteNode(pNode);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(IXMLDOMNode* pNode) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteXml();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<word>persnickety</word>
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|---------|-----------|
|[ptr::ptr](#ptr)|COM オブジェクト`com::ptr`をラップするを構築します。|
|[ptr::~ptr](#tilde-ptr)|を破棄します`com::ptr`。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|---------|-----------|
|[ptr::Attach](#attach)|COM オブジェクトを`com::ptr`にアタッチします。|
|[ptr::CreateInstance](#createInstance)|内に COM オブジェクトのインスタンスを`com::ptr`作成します。|
|[ptr::Detach](#detach)|COM オブジェクトの所有権を終了し、オブジェクトへのポインターを返します。|
|[ptr::GetInterface](#getInterface)|内に COM オブジェクトのインスタンスを`com::ptr`作成します。|
|[ptr::QueryInterface](#queryInterface)|所有している COM オブジェクトにインターフェイスを照会し、その結果を別`com::ptr`の .|
|[ptr::Release](#release)|COM オブジェクト上のすべての所有参照を解放します。|

### <a name="public-operators"></a>公共事業者

|名前|説明|
|---------|-----------|
|[ptr::演算子-&gt;](#operator-arrow)|所有している COM オブジェクトのメソッドを呼び出すために使用されるメンバー アクセス演算子。|
|[ptr::演算子=](#operator-assign)|COM オブジェクトを`com::ptr`にアタッチします。|
|[ptr::オペレーター&nbsp;・ブール](#operator-bool)|条件式で`com::ptr`使用する演算子。|
|[ptr::operator!](#operator-logical-not)|所有している COM オブジェクトが無効かどうかを判断する演算子。|

## <a name="requirements"></a>必要条件

**ヘッダー ファイル**\<msclr\com\ptr.h>

**名前空間**msclr::com

## <a name="ptrptr"></a><a name="ptr"></a>ptr::ptr

所有している COM オブジェクトへのポインターを返します。

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>パラメーター

*P*<br/>
COM インターフェイス ポインター。

### <a name="remarks"></a>解説

引数なしのコンストラクターは、`nullptr`基になるオブジェクト ハンドルに割り当てます。 今後の`com::ptr`呼び出しでは内部オブジェクトが検証され、オブジェクトが作成またはアタッチされるまで、通知なしに失敗します。

1 つの引数のコンストラクターは、COM オブジェクトへの参照を追加しますが、呼び出し元の参照を解放しないので`Release`、呼び出し元は COM オブジェクトを呼び出して、完全に制御を放棄する必要があります。 デストラ`com::ptr`クタが呼び出されると、COM オブジェクトに対する参照が自動的に解放されます。

この`NULL`コンストラクターへの渡しは、引数なしのバージョンを呼び出すことと同じです。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 この例では、両方のバージョンのコンストラクターの使用方法を示します。

```cpp
// comptr_ptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrptr"></a><a name="tilde-ptr"></a>ptr::~ptr

を破棄します`com::ptr`。

```cpp
~ptr();
```

### <a name="remarks"></a>解説

破棄すると、COM`com::ptr`オブジェクトに対して所有しているすべての参照が解放されます。 COM オブジェクトに対する他の参照が存在しないと仮定すると、COM オブジェクトは削除され、メモリは解放されます。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。  `main`この関数では、2`XmlDocument`つのオブジェクトのデストラクターが`try`ブロックのスコープ外に出ると呼び出され、その結果、基になる`com::ptr`デストラクターが呼び出され、COM オブジェクトへのすべての所有参照が解放されます。

```cpp
// comptr_dtor.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrattach"></a><a name="attach"></a>ptr::アタッチ

COM オブジェクトを`com::ptr`にアタッチします。

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>パラメーター

*_right*<br/>
アタッチする COM インターフェイス ポインター。

### <a name="exceptions"></a>例外

が既`com::ptr`に COM オブジェクトへの参照を所有`Attach`している場合<xref:System.InvalidOperationException>は、 がスローされます。

### <a name="remarks"></a>解説

COM オブジェクト`Attach`を参照する呼び出しは、呼び出し元の参照を解放しません。

結果`NULL`に`Attach`渡すと、アクションは実行されません。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 メンバー`ReplaceDocument`関数は、最初`Release`に所有されていたオブジェクトを呼び出`Attach`し、次に新しいドキュメント オブジェクトをアタッチする呼び出しを行います。

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>ptr::インスタンスの作成

内に COM オブジェクトのインスタンスを`com::ptr`作成します。

```cpp
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   System::String ^ progid
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   const wchar_t * progid
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter
);
void CreateInstance(
   REFCLSID rclsid
);
```

### <a name="parameters"></a>パラメーター

*Progid*<br/>
`ProgID` 文字列。

*パウター*<br/>
集約オブジェクトの IUnknown インターフェイス (制御 IUnknown) へのポインター。 指定`pouter`されていない場合は、`NULL`使用されます。

*cls_context*<br/>
新しく作成されたオブジェクトを管理するコードが実行されるコンテキスト。 値は列挙体から取得`CLSCTX`されます。 指定`cls_context`しない場合は、CLSCTX_ALL値が使用されます。

*rclsid*<br/>
`CLSID`オブジェクトの作成に使用されるデータおよびコードに関連付けられます。

### <a name="exceptions"></a>例外

が既`com::ptr`に COM オブジェクトへの参照を所有`CreateInstance`している場合<xref:System.InvalidOperationException>は、 がスローされます。

この関数は`CoCreateInstance`、エラー<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>`HRESULT`を適切な例外に変換するために呼び出し、使用します。

### <a name="remarks"></a>解説

`CreateInstance`は`CoCreateInstance`、ProgID または CLSID から識別される、指定されたオブジェクトの新しいインスタンスを作成するために使用されます。 新`com::ptr`しく作成されたオブジェクトを参照し、破棄時に所有されているすべての参照を自動的に解放します。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 クラス コンストラクターは、 の 2`CreateInstance`つの異なる形式を使用して、ProgID または CLSID と CLSCTX からドキュメント オブジェクトを作成します。

```cpp
// comptr_createinstance.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }
   XmlDocument(REFCLSID clsid, DWORD clsctx) {
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc1("Msxml2.DOMDocument.3.0");

      // or from a clsid with specific CLSCTX
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

## <a name="ptrdetach"></a><a name="detach"></a>ptr::Dエタッハ

COM オブジェクトの所有権を終了し、オブジェクトへのポインターを返します。

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>戻り値

COM オブジェクトへのポインター。

オブジェクトが所有されていない場合は、NULL が返されます。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface`所有する COM オブジェクトに対して呼`HRESULT`び出され、エラーは<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によって例外に変換されます。

### <a name="remarks"></a>解説

`Detach`まず呼び出し元に代わって COM オブジェクトへの参照を追加し、次に`com::ptr`が所有するすべての参照を解放します。  呼び出し元は、最終的に、返されたオブジェクトを解放して破棄する必要があります。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。  COM`DetachDocument`オブジェクトの`Detach`所有権を放棄し、呼び出し元へのポインターを返すメンバー関数を呼び出します。

```cpp
// comptr_detach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

## <a name="ptrgetinterface"></a><a name="getInterface"></a>ptr::インターフェイスを取得します。

所有している COM オブジェクトへのポインターを返します。

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>戻り値

所有している COM オブジェクトへのポインター。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface`所有する COM オブジェクトに対して呼`HRESULT`び出され、エラーは<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によって例外に変換されます。

### <a name="remarks"></a>解説

呼`com::ptr`び出し元の代わりに COM オブジェクトへの参照を追加し、COM オブジェクトに対する独自の参照も保持します。 呼び出し元は、最終的に返されたオブジェクトの参照を解放する必要があります。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 メンバー`GetDocument`関数は、COM オブジェクトへのポインターを返すために使用`GetInterface`します。

```cpp
// comptr_getinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>ptr::クエリインターフェイス

所有している COM オブジェクトにインターフェイスを照会し、その結果を別`com::ptr`の .

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>パラメーター

*他*<br/>
`com::ptr`インターフェイスを取得します。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface`所有する COM オブジェクトに対して呼`HRESULT`び出され、エラーは<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によって例外に変換されます。

### <a name="remarks"></a>解説

このメソッドは、現在のラッパーが所有する COM オブジェクトの別のインターフェイスに対して COM ラッパーを作成するために使います。 このメソッドは`QueryInterface`、所有する COM オブジェクトを通じて COM オブジェクトの特定のインターフェイスへのポインターを要求し、返されたインターフェイス ポインター`com::ptr`を渡されたインターフェイス にアタッチします。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 メンバー`WriteTopLevelNode`関数は、`QueryInterface`を`com::ptr``IXMLDOMNode`使用してローカルにを埋め込み`com::ptr`、ノードの名前とテキスト プロパティをコンソールに書き込むプライベート メンバー関数に (追跡参照によって) 渡します。

```cpp
// comptr_queryinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into our document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // write the top level node to the console
   void WriteTopLevelNode() {
      com::ptr<IXMLDOMNode> ptrNode;

      // query for the top level node interface
      m_ptrDoc.QueryInterface(ptrNode);
      WriteNode(ptrNode);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(com::ptr<IXMLDOMNode> % node) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(node->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteTopLevelNode();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<#document>persnickety</#document>
```

## <a name="ptrrelease"></a><a name="release"></a>ptr::リリース

COM オブジェクト上のすべての所有参照を解放します。

```cpp
void Release();
```

### <a name="remarks"></a>解説

この関数を呼び出すと、COM オブジェクト上のすべての所有参照が解放され、内部ハンドル`nullptr`が COM オブジェクトに設定されます。  COM オブジェクトに他の参照が存在しない場合、その参照は破棄されます。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。  この`ReplaceDocument`メンバー関数は`Release`、新しいドキュメントを添付する前に、以前のドキュメント オブジェクトを解放するために使用します。

```cpp
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>ptr::演算子-&gt;

所有している COM オブジェクトのメソッドを呼び出すために使用されるメンバー アクセス演算子。

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>戻り値

COM`smart_com_ptr`オブジェクトへの A。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface`所有する COM オブジェクトに対して呼`HRESULT`び出され、エラーは<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によって例外に変換されます。

### <a name="remarks"></a>解説

この演算子を使用すると、所有されている COM オブジェクトのメソッドを呼び出すことができます。 このメソッドは、`smart_com_ptr`独自`AddRef`のと を自動的`Release`に処理する一時を返します。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 この`WriteDocument`関数は`operator->`、ドキュメント`get_firstChild`オブジェクトのメンバーを呼び出すために使用します。

```cpp
// comptr_op_member.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="ptroperator"></a><a name="operator-assign"></a>ptr::演算子=

COM オブジェクトを`com::ptr`にアタッチします。

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>パラメーター

*_right*<br/>
アタッチする COM インターフェイス ポインター。

### <a name="return-value"></a>戻り値

の追跡参照`com::ptr`。

### <a name="exceptions"></a>例外

が既`com::ptr`に COM オブジェクトへの参照を所有`operator=`している場合<xref:System.InvalidOperationException>は、 がスローされます。

### <a name="remarks"></a>解説

COM オブジェクトを COM`com::ptr`オブジェクトへの割り当ては COM オブジェクトを参照しますが、呼び出し元の参照は解放されません。

この演算子は、 と同`Attach`じ効果を持ちます。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。  メンバー`ReplaceDocument`関数は、最初`Release`に所有されているオブジェクトを呼び出`operator=`し、次に新しいドキュメント オブジェクトのアタッチに使用します。

```cpp
// comptr_op_assign.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>ptr::オペレーター・ブール

条件式で`com::ptr`使用する演算子。

```cpp
operator bool();
```

### <a name="return-value"></a>戻り値

`true`所有している COM オブジェクトが有効な場合。`false`それ以外の場合。

### <a name="remarks"></a>解説

所有している COM オブジェクトが有効でない`nullptr`場合は有効です。

この演算子は、整数`_detail_class::_safe_bool`型に変換できないため`bool`、より安全に変換されます。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。 メンバー`CreateInstance`関数は、`operator bool`新しいドキュメント オブジェクトを作成した後に、有効かどうかを判断し、有効な場合はコンソールに書き込みを行います。

```cpp
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="ptroperator"></a><a name="operator-logical-not"></a>ptr::オペレーター!

所有している COM オブジェクトが無効かどうかを判断する演算子。

```cpp
bool operator!();
```

### <a name="return-value"></a>戻り値

`true`所有している COM オブジェクトが無効な場合。`false`それ以外の場合。

### <a name="remarks"></a>解説

所有している COM オブジェクトが有効でない`nullptr`場合は有効です。

### <a name="example"></a>例

この例では、 を使用してプライベート`com::ptr`メンバー`IXMLDOMDocument`オブジェクトをラップする CLR クラスを実装します。  この`CreateInstance`メンバー関数は`operator!`、ドキュメント オブジェクトが既に所有されているかどうかを判断するために使用し、オブジェクトが無効な場合にのみ新しいインスタンスを作成します。

```cpp
// comptr_op_not.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) {
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```
