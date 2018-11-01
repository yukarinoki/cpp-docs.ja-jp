---
title: com::ptr Class
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- com::ptr
- msclr::com::ptr
- msclr.com.ptr
- com.ptr
helpviewer_keywords:
- ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: c4d5818698f553fe1d003aab6ca3c7f31e85f843
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665365"
---
# <a name="comptr-class"></a>com::ptr Class

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパーです。  また、ラッパーには、そのデストラクターが呼び出されたときに、オブジェクトを所有しているすべての参照を解放し、COM オブジェクトの有効期間管理が自動化されます。 類似しています[CComPtr クラス](../atl/reference/ccomptr-class.md)します。

## <a name="syntax"></a>構文

```
template<class _interface_type>
ref class ptr;
```

#### <a name="parameters"></a>パラメーター

*_interface_type*<br/>
COM インターフェイスです。

## <a name="remarks"></a>Remarks

A `com::ptr` COM のさまざまなタスクを簡略化および有効期間管理を自動化するもローカル関数の変数としては使用できます。

A`com::ptr`関数のパラメーターとして直接使用することはできません。 使用して、[参照演算子の追跡](../windows/tracking-reference-operator-cpp-component-extensions.md)または[オブジェクト演算子 (^) へのハンドル](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)代わりにします。

A`com::ptr`関数から直接返されることはできません。 代わりに、ハンドルを使用します。

## <a name="example"></a>例

この例の実装を使用する CLR クラス、`com::ptr`のプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。  クラスの結果のパブリック メソッドを呼び出し、格納されている呼び出しで`IXMLDOMDocument`オブジェクト。  サンプルは、XML ドキュメントのインスタンスを作成し、簡単な XML が格納、簡単に、コンソールに XML を出力する解析済みドキュメント ツリー内のノードの走査。

```
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

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>関連項目

[C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)<br/>
[ptr のメンバー](../dotnet/ptr-members.md)