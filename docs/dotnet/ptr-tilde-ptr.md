---
title: 'ptr:: ~ ptr |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr.com.ptr.~ptr
- ptr.~ptr
- msclr::com.ptr::~ptr
- ~ptr
- ptr::~ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr::~ptr
ms.assetid: 5f644aa5-fe66-4992-a5f8-13ec1292c949
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e3457bb4bda5e08de676488d6100795b5c04b61a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399577"
---
# <a name="ptrptr"></a>ptr::~ptr

Destructs、`com::ptr`します。

## <a name="syntax"></a>構文

```
~ptr();
```

## <a name="remarks"></a>Remarks

破棄、`com::ptr`その COM オブジェクトを所有しているすべての参照を解放します。 COM オブジェクトに保持されているその他の参照がないと仮定 COM オブジェクトが削除され、そのメモリを解放します。

## <a name="example"></a>例

この例の実装を使用する CLR クラス、`com::ptr`のプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。  `main`関数では、2 つ`XmlDocument`のスコープ外に出るときに、オブジェクトのデストラクターが呼び出される、`try`ブロック、その結果、基になる`com::ptr`デストラクターが呼び出される COM を所有しているすべての参照を解放オブジェクト。

```
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

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>関連項目

[ptr のメンバー](../dotnet/ptr-members.md)<br/>
[ptr::ptr](../dotnet/ptr-ptr.md)<br/>
[ptr::CreateInstance](../dotnet/ptr-createinstance.md)