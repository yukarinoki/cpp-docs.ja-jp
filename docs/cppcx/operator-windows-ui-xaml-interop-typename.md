---
description: '詳細については、「operator Windows:: UI:: Xaml:: Interop:: TypeName」を参照してください。'
title: Windows::UI::Xaml::Interop::TypeName 演算子
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 3c4c856fcf93214959f75f861b035dbdee9b94a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145718"
---
# <a name="operator-windowsuixamlinteroptypename"></a>Windows::UI::Xaml::Interop::TypeName 演算子

`Platform::Type` から [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename)変換できるようになります。

## <a name="syntax"></a>構文

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>戻り値

[が指定されていると、](/uwp/api/windows.ui.xaml.interop.typename) Windows::UI::Xaml::Interop::TypeName `Platform::Type^`が返されます。

### <a name="remarks"></a>解説

`TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。 [Platform::Type](../cppcx/platform-type-class.md) は C++ に固有で、アプリケーション バイナリ インターフェイス (ABI: Application Binary Interface) を通じて渡すことはできません。 `TypeName`Navigate [関数での](/uwp/api/windows.ui.xaml.controls.frame.navigate) の使用例を次に示します。

```cpp
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>例

次に、 `TypeName` と `Type`の間の変換方法を示します。

```cpp
// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数

プログラムプロジェクト `TypeName` を system.string [](/dotnet/api/system.type)として .NET Framework します。

### <a name="requirements"></a>要件

## <a name="see-also"></a>関連項目

[Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform:: Type クラス](../cppcx/platform-type-class.md)
