---
title: Platform::Metadata::RuntimeClassName
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
ms.openlocfilehash: 09641f55e27ab00fc941d85d4d09d6a7784e2d8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668274"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName

クラス定義に適用された場合、プライベート クラスが GetRuntimeClassName 関数から有効な名前を返すことを確認します。

## <a name="syntax"></a>構文

```cpp
[Platform::Metadata::RuntimeClassName] name
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
Windows ランタイムで表示される既存のパブリックの種類の名前です。

### <a name="remarks"></a>Remarks

プライベート ref クラスのこの属性を使用して、カスタム ランタイムの種類の名前、および既存の名前が要件を満たさない場合を指定します。 名前としてクラスが実装するパブリック インターフェイスを指定します。

### <a name="example"></a>例

この属性を使用する方法の例を次に示します。 この例では、HellowWorldImpl のランタイムの種類の名前は Test::Native::MyComponent::IHelloWorld です。

```cpp
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