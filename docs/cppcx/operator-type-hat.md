---
description: 詳細については、「演算子の種類 ^」を参照してください。
title: Type^ 演算子
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: 6258da5f276313d28f56fe470849c929cc057a47
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276804"
---
# <a name="operator-type"></a>Type^ 演算子

[Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) から `Platform::Type`への変換を有効にします。

## <a name="syntax"></a>構文

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>戻り値

`Platform::Type` Windows::UI::Xaml::Interop::TypeName [が指定されると、](/uwp/api/windows.ui.xaml.interop.typename)を返します。

### <a name="remarks"></a>解説

`TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。 [Platform::Type](../cppcx/platform-type-class.md) は C++ に固有で、アプリケーション バイナリ インターフェイス (ABI: Application Binary Interface) を通じて渡すことはできません。 `TypeName`Navigate [関数での](/uwp/api/windows.ui.xaml.controls.frame.navigate) の使用例を次に示します。

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>例

次に、 `TypeName` と `Type`の間の変換方法を示します。

```

// Convert from Type to TypeName
TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

.NET Framework `TypeName` プログラムプロジェクト <xref:System.Type>

### <a name="requirements"></a>要件

## <a name="see-also"></a>関連項目

[Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform:: Type クラス](../cppcx/platform-type-class.md)
