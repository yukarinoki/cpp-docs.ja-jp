---
description: '詳細情報: Platform:: Type クラス'
title: Platform::Type クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: c11e85180dfb3eeeeb6eea88c3bd47b40fa7289b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307900"
---
# <a name="platformtype-class"></a>Platform::Type クラス

型に関するランタイム情報 (文字列名と型コード) を含みます。 任意のオブジェクトで [object:: GetType](../cppcx/platform-object-class.md#gettype) を呼び出すか、クラスまたは構造体名で [typeid](../extensions/typeid-cpp-component-extensions.md) 演算子を使用することによって取得されます。

## <a name="syntax"></a>構文

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>解説

クラスは、 `Type` **`if`** **`switch`** オブジェクトの実行時の型に基づいて分岐するステートメントまたはステートメントを使用して処理を指示する必要があるアプリケーションで役に立ちます。 型のカテゴリを記述する型コードは、 [type:: gettypecode](#gettypecode) 型のメンバー関数を使用して取得されます。

## <a name="public-methods"></a>パブリック メソッド

| 名前 | 説明 |
|--|--|
| [Type::GetTypeCode メソッド](#gettypecode) | オブジェクトの [Platform::TypeCode 列挙](../cppcx/platform-typecode-enumeration.md) 値を返します。 |
| [Type:: ToString メソッド](#tostring) | メタデータで指定されている型の名前を返します。 |

## <a name="public-properties"></a>パブリック プロパティ

| 名前 | 説明 |
|--|--|
| [Type:: FullName](#fullname) | 返します、 [platform::string Class](../cppcx/platform-string-class.md)^ 型の完全修飾名を表し、を使用している。 (ドット) は区切り記号として、:: (二重コロン) ではありません。たとえば、のように `MyNamespace.MyClass` なります。 |

## <a name="conversion-operators"></a>変換演算子

| 名前 | 説明 |
|--|--|
| [演算子の種類 ^](../cppcx/operator-type-hat.md) | `Windows::UI::Xaml::Interop::TypeName` から `Platform::Type`への変換を有効にします。 |
| [Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-windows-ui-xaml-interop-typename.md) | `Platform::Type` から `Windows::UI::Xaml::Interop::TypeName`への変換を有効にします。 |

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="typefullname-property"></a><a name="fullname"></a> Type:: FullName プロパティ

フォーム内の現在の型の完全修飾名を取得 `Namespace.Type` します。

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

## <a name="typegettypecode-method"></a><a name="gettypecode"></a> Type:: GetTypeCode 種類のメソッド

組み込み型の数値型カテゴリを取得します。

### <a name="syntax"></a>構文

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>戻り値

Platform::TypeCode 列挙値のいずれか。

### <a name="remarks"></a>解説

GetTypeCode のメンバーメソッドに相当するのは **`typeid`** プロパティです。

## <a name="typetostring-method"></a><a name="tostring"></a> Type:: ToString メソッド

型の名前を取得します。

### <a name="syntax"></a>構文

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>戻り値

メタデータで指定されている型の名前。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
