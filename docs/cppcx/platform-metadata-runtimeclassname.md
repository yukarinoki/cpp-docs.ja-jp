---
title: Platform::Metadata::RuntimeClassName |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 024d9d7dce234b07620a108b1f11c240bd842ac6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765489"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName
クラス定義に適用された場合、プライベート クラスが GetRuntimeClassName 関数から有効な名前を返すことを確認します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### <a name="parameters"></a>パラメーター  
 name  
  
 Windows ランタイムで表示される既存のパブリックの種類の名前です。  
  
### <a name="remarks"></a>Remarks  
 プライベート ref クラスのこの属性を使用して、カスタム ランタイムの種類の名前、および既存の名前が要件を満たさない場合を指定します。 名前としてクラスが実装するパブリック インターフェイスを指定します。  
  
### <a name="example"></a>例  
 この属性を使用する方法の例を次に示します。 この例では、HellowWorldImpl のランタイムの種類の名前は Test::Native::MyComponent::IHelloWorld です。  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Platform::Metadata 名前空間](../cppcx/platform-metadata-namespace.md)