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
ms.openlocfilehash: 8a3223543dfa6c1b5b45fef2780cd11b558eab84
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078964"
---
# <a name="comptr-class"></a>com::ptr Class

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパー。  また、ラッパーは、COM オブジェクトの有効期間の管理も自動化し、デストラクターが呼び出されたときに、オブジェクトに対して所有されているすべての参照を解放します。 [CComPtr クラス](../atl/reference/ccomptr-class.md)に似ています。

## <a name="syntax"></a>構文

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>パラメーター

*_interface_type*<br/>
COM インターフェイス。

## <a name="remarks"></a>解説

また、`com::ptr` をローカル関数変数として使用して、さまざまな COM タスクを簡略化し、有効期間管理を自動化することもできます。

`com::ptr` を関数パラメーターとして直接使用することはできません。代わりに、[追跡参照演算子](../extensions/tracking-reference-operator-cpp-component-extensions.md)または[オブジェクト演算子 (^) へのハンドル](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)を使用してください。

`com::ptr` を関数から直接返すことはできません。代わりにハンドルを使用してください。

## <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。  クラスのパブリックメソッドを呼び出すと、含まれている `IXMLDOMDocument` オブジェクトが呼び出されます。  このサンプルでは、XML ドキュメントのインスタンスを作成し、そのインスタンスに単純な XML を格納します。また、解析されたドキュメントツリー内のノードを簡略化して、XML をコンソールに出力します。

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

|Name|Description|
|---------|-----------|
|[ptr::ptr](#ptr)|COM オブジェクトをラップする `com::ptr` を構築します。|
|[ptr::~ptr](#tilde-ptr)|`com::ptr`を Destructs します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|---------|-----------|
|[ptr::Attach](#attach)|COM オブジェクトを `com::ptr`にアタッチします。|
|[ptr::CreateInstance](#createInstance)|`com::ptr`内に COM オブジェクトのインスタンスを作成します。|
|[ptr::Detach](#detach)|オブジェクトへのポインターを返す COM オブジェクトの所有権を取得します。|
|[ptr::GetInterface](#getInterface)|`com::ptr`内に COM オブジェクトのインスタンスを作成します。|
|[ptr::QueryInterface](#queryInterface)|所有されている COM オブジェクトに対してインターフェイスを照会し、その結果を別の `com::ptr`にアタッチします。|
|[ptr::Release](#release)|COM オブジェクトに対して所有されているすべての参照を解放します。|

### <a name="public-operators"></a>パブリック演算子

|Name|Description|
|---------|-----------|
|[ptr:: operator-&gt;](#operator-arrow)|メンバーアクセス演算子。所有している COM オブジェクトのメソッドを呼び出すために使用されます。|
|[ptr::operator=](#operator-assign)|COM オブジェクトを `com::ptr`にアタッチします。|
|[ptr:: operator&nbsp;bool](#operator-bool)|条件式で `com::ptr` を使用するための演算子。|
|[ptr::operator!](#operator-logical-not)|所有している COM オブジェクトが無効かどうかを判断する演算子。|

## <a name="requirements"></a>必要条件

**ヘッダーファイル**\<msclr\com\ptr.h >

**名前空間**msclr:: com

## <a name="ptrptr"></a><a name="ptr"></a>ptr::p tr

所有されている COM オブジェクトへのポインターを返します。

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

引数なしのコンストラクターは、基になるオブジェクトハンドルに `nullptr` を割り当てます。 今後、`com::ptr` を呼び出すと、内部オブジェクトが検証され、オブジェクトが作成またはアタッチされるまで、警告なしに失敗します。

1つの引数を持つコンストラクターは、COM オブジェクトへの参照を追加しますが、呼び出し元の参照を解放しません。そのため、呼び出し元は COM オブジェクトの `Release` を呼び出して、実際にコントロールを提供する必要があります。 `com::ptr`のデストラクターが呼び出されると、COM オブジェクトに対するその参照が自動的に解放されます。

このコンストラクターに `NULL` を渡すことは、引数なしのバージョンを呼び出すことと同じです。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 この例では、両方のバージョンのコンストラクターの使用方法を示しています。

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

## <a name="ptrptr"></a><a name="tilde-ptr"></a>ptr:: ~ ptr

`com::ptr`を Destructs します。

```cpp
~ptr();
```

### <a name="remarks"></a>解説

破棄時には、`com::ptr` によって、その COM オブジェクトに対して所有されているすべての参照が解放されます。 COM オブジェクトに他の参照が保持されていないと仮定すると、COM オブジェクトが削除され、そのメモリが解放されます。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。  `main` 関数では、2つの `XmlDocument` オブジェクトのデストラクターが `try` ブロックのスコープから出たときに呼び出されます。その結果、基になる `com::ptr` デストラクターが呼び出され、COM オブジェクトへのすべての所有参照が解放されます。

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

## <a name="ptrattach"></a><a name="attach"></a>ptr:: Attach

COM オブジェクトを `com::ptr`にアタッチします。

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>パラメーター

*_right*<br/>
アタッチする COM インターフェイスポインター。

### <a name="exceptions"></a>例外

`com::ptr` が COM オブジェクトへの参照を既に所有している場合、`Attach` は <xref:System.InvalidOperationException>をスローします。

### <a name="remarks"></a>解説

`Attach` の呼び出しは COM オブジェクトを参照しますが、呼び出し元の参照を解放しません。

`Attach` に `NULL` を渡すと、アクションは実行されません。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 `ReplaceDocument` メンバー関数は、最初に以前に所有されたオブジェクトで `Release` を呼び出し、次に `Attach` を呼び出して新しいドキュメントオブジェクトをアタッチします。

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

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>ptr:: CreateInstance

`com::ptr`内に COM オブジェクトのインスタンスを作成します。

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

*progid*<br/>
`ProgID` 文字列。

*pouter*<br/>
集約オブジェクトの IUnknown インターフェイス (制御 IUnknown) へのポインター。 `pouter` が指定されていない場合、`NULL` が使用されます。

*cls_context*<br/>
新しく作成されたオブジェクトを管理するコードが実行されるコンテキスト。 値は `CLSCTX` 列挙体から取得されます。 `cls_context` が指定されていない場合は CLSCTX_ALL 値が使用されます。

*rclsid*<br/>
オブジェクトの作成に使用されるデータとコードに関連付けられている `CLSID`。

### <a name="exceptions"></a>例外

`com::ptr` が COM オブジェクトへの参照を既に所有している場合、`CreateInstance` は <xref:System.InvalidOperationException>をスローします。

この関数は `CoCreateInstance` を呼び出し、<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> を使用してエラー `HRESULT` を適切な例外に変換します。

### <a name="remarks"></a>解説

`CreateInstance` は、`CoCreateInstance` を使用して、ProgID または CLSID から識別される、指定されたオブジェクトの新しいインスタンスを作成します。 `com::ptr` は、新しく作成されたオブジェクトを参照し、破棄時に所有されているすべての参照を自動的に解放します。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 クラスコンストラクターは2つの異なる形式の `CreateInstance` を使用して、ProgID または CLSID と CLSCTX の両方からドキュメントオブジェクトを作成します。

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

## <a name="ptrdetach"></a><a name="detach"></a>ptr::D

オブジェクトへのポインターを返す COM オブジェクトの所有権を取得します。

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>戻り値

COM オブジェクトへのポインター。

オブジェクトが所有されていない場合は、NULL が返されます。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface` が所有されている COM オブジェクトで呼び出され、<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によってエラー `HRESULT` が例外に変換されます。

### <a name="remarks"></a>解説

`Detach` は、最初に呼び出し元に代わって COM オブジェクトへの参照を追加し、次に `com::ptr`が所有するすべての参照を解放します。  呼び出し元は、返されたオブジェクトを破棄するために最終的に解放する必要があります。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。  `DetachDocument` メンバー関数は、`Detach` を呼び出して、COM オブジェクトの所有権を取得し、呼び出し元へのポインターを返します。

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

## <a name="ptrgetinterface"></a><a name="getInterface"></a>ptr:: GetInterface

所有されている COM オブジェクトへのポインターを返します。

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>戻り値

所有されている COM オブジェクトへのポインター。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface` が所有されている COM オブジェクトで呼び出され、<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によってエラー `HRESULT` が例外に変換されます。

### <a name="remarks"></a>解説

`com::ptr` は、呼び出し元の代わりに COM オブジェクトへの参照を追加し、COM オブジェクトに対する独自の参照も保持します。 呼び出し元は、返されたオブジェクトの参照を最終的に解放する必要があります。そうしないと、破棄されません。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 `GetDocument` メンバー関数は、`GetInterface` を使用して、COM オブジェクトへのポインターを返します。

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

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>ptr:: QueryInterface

所有されている COM オブジェクトに対してインターフェイスを照会し、その結果を別の `com::ptr`にアタッチします。

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>パラメーター

*other*<br/>
インターフェイスを取得する `com::ptr`。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface` が所有されている COM オブジェクトで呼び出され、<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によってエラー `HRESULT` が例外に変換されます。

### <a name="remarks"></a>解説

このメソッドを使用して、現在のラッパーによって所有されている COM オブジェクトの別のインターフェイスの COM ラッパーを作成します。 このメソッドは、所有されている COM オブジェクトを介して `QueryInterface` を呼び出し、COM オブジェクトの特定のインターフェイスへのポインターを要求し、返されたインターフェイスポインターを渡された `com::ptr`にアタッチします。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 `WriteTopLevelNode` メンバー関数は、`QueryInterface` を使用してローカル `com::ptr` に `IXMLDOMNode` を設定し、`com::ptr` (追跡参照) をノードの名前とテキストのプロパティをコンソールに書き込むプライベートメンバー関数に渡します。

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

## <a name="ptrrelease"></a><a name="release"></a>ptr:: Release

COM オブジェクトに対して所有されているすべての参照を解放します。

```cpp
void Release();
```

### <a name="remarks"></a>解説

この関数を呼び出すと、COM オブジェクトに対して所有されているすべての参照が解放され、COM オブジェクトへの内部ハンドルが `nullptr`に設定されます。  COM オブジェクトに他の参照が存在しない場合は、破棄されます。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。  `ReplaceDocument` メンバー関数は、`Release` を使用して、新しいドキュメントをアタッチする前に、前のドキュメントオブジェクトを解放します。

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

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>ptr:: operator-&gt;

メンバーアクセス演算子。所有している COM オブジェクトのメソッドを呼び出すために使用されます。

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>戻り値

COM オブジェクトへの `smart_com_ptr`。

### <a name="exceptions"></a>例外

内部的には、`QueryInterface` が所有されている COM オブジェクトで呼び出され、<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>によってエラー `HRESULT` が例外に変換されます。

### <a name="remarks"></a>解説

この演算子を使用すると、所有されている COM オブジェクトのメソッドを呼び出すことができます。 このメソッドは、独自の `AddRef` と `Release`を自動的に処理する一時 `smart_com_ptr` を返します。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 `WriteDocument` 関数は、`operator->` を使用して、document オブジェクトの `get_firstChild` メンバーを呼び出します。

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

## <a name="ptroperator"></a><a name="operator-assign"></a>ptr:: operator =

COM オブジェクトを `com::ptr`にアタッチします。

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>パラメーター

*_right*<br/>
アタッチする COM インターフェイスポインター。

### <a name="return-value"></a>戻り値

`com::ptr`の追跡参照。

### <a name="exceptions"></a>例外

`com::ptr` が COM オブジェクトへの参照を既に所有している場合、`operator=` は <xref:System.InvalidOperationException>をスローします。

### <a name="remarks"></a>解説

COM オブジェクトを `com::ptr` に割り当てると COM オブジェクトが参照されますが、呼び出し元の参照は解放されません。

この演算子は `Attach`と同じ効果があります。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。  `ReplaceDocument` メンバー関数は、最初に以前に所有されたオブジェクトで `Release` を呼び出し、次に `operator=` を使用して新しいドキュメントオブジェクトをアタッチします。

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

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>ptr:: operator bool

条件式で `com::ptr` を使用するための演算子。

```cpp
operator bool();
```

### <a name="return-value"></a>戻り値

所有されている COM オブジェクトが有効である場合に `true` します。それ以外の場合は `false`。

### <a name="remarks"></a>解説

所有されている COM オブジェクトは、`nullptr`ない場合は有効です。

この演算子は、整数型に変換できないため、`bool` よりも安全な `_detail_class::_safe_bool` に変換されます。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。 `CreateInstance` メンバー関数は、新しいドキュメントオブジェクトを作成した後に `operator bool` を使用して、そのオブジェクトが有効かどうかを判断し、そのオブジェクトが存在する場合はコンソールに書き込みます。

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

## <a name="ptroperator"></a><a name="operator-logical-not"></a>ptr:: operator!

所有している COM オブジェクトが無効かどうかを判断する演算子。

```cpp
bool operator!();
```

### <a name="return-value"></a>戻り値

所有されている COM オブジェクトが無効である場合に `true` します。それ以外の場合は `false`。

### <a name="remarks"></a>解説

所有されている COM オブジェクトは、`nullptr`ない場合は有効です。

### <a name="example"></a>例

この例では、`com::ptr` を使用してプライベートメンバー `IXMLDOMDocument` オブジェクトをラップする CLR クラスを実装しています。  `CreateInstance` メンバー関数は、`operator!` を使用して、ドキュメントオブジェクトが既に所有されているかどうかを判断し、オブジェクトが無効な場合にのみ新しいインスタンスを作成します。

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
