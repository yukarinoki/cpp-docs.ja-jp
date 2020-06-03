---
title: Platform::Type クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: 7463a2518e6ec5cc84f59db05cfaf60e43eb9fde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322095"
---
# <a name="platformtype-class"></a>Platform::Type クラス

型に関するランタイム情報 (文字列名と型コード) を含みます。 任意のオブジェクトに対して[Object::GetType](../cppcx/platform-object-class.md#gettype)を呼び出すか、クラス名または構造体名に[typeid](../extensions/typeid-cpp-component-extensions.md)演算子を使用して取得されます。

## <a name="syntax"></a>構文

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>解説

`Type` クラスは、オブジェクトの実行時の型に基づいて分岐する `if` ステートメントまたは `switch` ステートメントを使用して処理を指示する必要があるアプリケーションで役に立ちます。 型のカテゴリを記述する型コードは、[型::GetTypeCode](#gettypecode)メンバー関数を使用して取得されます。

## <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|[Type::GetTypeCode メソッド](#gettypecode)|オブジェクトの [Platform::TypeCode 列挙](../cppcx/platform-typecode-enumeration.md) 値を返します。|
|[型::ToString メソッド](#tostring)|メタデータで指定された型の名前を返します。|

## <a name="public-properties"></a>パブリック プロパティ

|||
|-|-|
|[タイプ::フルネーム](#fullname)|返します、 [platform::string Class](../cppcx/platform-string-class.md)^ 型の完全修飾名を表し、を使用している。 (ドット) は、:: (二重コロン) などではなく、`MyNamespace.MyClass`区切り記号として.|

## <a name="conversion-operators"></a>変換演算子

|||
|-|-|
|[演算子 型^](../cppcx/operator-type-hat.md)|`Windows::UI::Xaml::Interop::TypeName` から `Platform::Type`への変換を有効にします。|
|[Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-windows-ui-xaml-interop-typename.md)|`Platform::Type` から `Windows::UI::Xaml::Interop::TypeName`への変換を有効にします。|

### <a name="requirements"></a>必要条件

**サポートされる最小クライアント:** ウィンドウズ 8

**サポートされる最小サーバー:** ウィンドウズ サーバー 2012

**名前空間:** Platform

**メタデータ:** プラットフォーム.winmd

## <a name="typefullname-property"></a><a name="fullname"></a>タイプ::フルネームプロパティ

フォーム`Namespace.Type`内の現在の型の完全修飾名を取得します。

### <a name="syntax"></a>構文

```cpp
String^ FullName();
```

### <a name="return-value"></a>戻り値

型の名前。

### <a name="example"></a>例

```cpp
//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="typegettypecode-method"></a><a name="gettypecode"></a>型::GetType コード メソッド

組み込み型の数値型カテゴリを取得します。

### <a name="syntax"></a>構文

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>戻り値

Platform::TypeCode 列挙値のいずれか。

### <a name="remarks"></a>解説

`typeid` プロパティが GetTypeCode() メンバー メソッドに相当します。

## <a name="typetostring-method"></a><a name="tostring"></a>型::ToString メソッド

型の名前を取得します。

### <a name="syntax"></a>構文

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>戻り値

メタデータで指定された型の名前。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
