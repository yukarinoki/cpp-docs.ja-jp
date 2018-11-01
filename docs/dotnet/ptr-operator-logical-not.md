---
title: ptr::operator!
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr::operator!
- msclr::com::ptr::operator!
- ptr.operator!
- msclr.com.ptr.operator!
helpviewer_keywords:
- ptr::operator!
ms.assetid: 7f4101dc-2045-42e7-abb1-6a30e17147f2
ms.openlocfilehash: 8527afe20bf0b0896f2bd433b3dd3e4e8057357b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580896"
---
# <a name="ptroperator"></a>ptr::operator!

所有されている COM オブジェクトが有効であるかを決定する演算子です。

## <a name="syntax"></a>構文

```
bool operator!();
```

## <a name="return-value"></a>戻り値

**true**所有されている COM オブジェクトが無効である場合**false**それ以外の場合。

## <a name="remarks"></a>Remarks

所有されている COM オブジェクトがない場合は、有効では**nullptr**します。

## <a name="example"></a>例

この例の実装を使用する CLR クラス、`com::ptr`のプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。  `CreateInstance`メンバー関数を使用して`operator!`ドキュメント オブジェクトを既に所有するいると、オブジェクトが有効でない場合にのみ新しいインスタンスを作成します。

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

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>関連項目

[ptr のメンバー](../dotnet/ptr-members.md)<br/>
[ptr::operator bool](../dotnet/ptr-operator-bool.md)