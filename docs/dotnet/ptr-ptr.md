---
title: ptr::ptr |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr::ptr
- ptr.ptr
- msclr.com.ptr.ptr
- msclr::com::ptr::ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr::ptr
ms.assetid: 4f5883b4-7c0a-46c6-aa9f-4e49eed463eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0cd8b4a4a1140a1a34e0148756cdb23b2f8069cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161474"
---
# <a name="ptrptr"></a>ptr::ptr
構築、`com::ptr`を COM オブジェクトをラップします。  
  
## <a name="syntax"></a>構文  
  
```  
ptr();  
ptr(  
   _interface_type * p  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `P`  
 COM インターフェイス ポインター。  
  
## <a name="remarks"></a>コメント  
 引数を受け取らないコンス トラクターが代入`nullptr`を基になるオブジェクトのハンドル。 後続の呼び出し、`com::ptr`内部オブジェクトを検証し、オブジェクトが実際に作成またはアタッチされるまで、サイレント モードで失敗します。  
  
 引数が 1 つのコンス トラクターは、COM オブジェクトへの参照を追加しますが、呼び出し元の参照を解放しないため、呼び出し元を呼び出す必要があります`Release`本当に制御を放棄する COM オブジェクトにします。 ときに、`com::ptr`のデストラクターが呼び出される COM オブジェクトへの参照を自動的に解放します。  
  
 渡す`NULL`このコンス トラクターには、引数なしのバージョンの呼び出しと同じです。  
  
## <a name="example"></a>例  
 この例を使用して CLR クラスを実装して、`com::ptr`をそのプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。 コンス トラクターの両方のバージョンの使用方法を示します。  
  
```  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>関連項目  
 [ptr メンバー](../dotnet/ptr-members.md)   
 [ptr::CreateInstance](../dotnet/ptr-createinstance.md)   
 [ptr::~ptr](../dotnet/ptr-tilde-ptr.md)