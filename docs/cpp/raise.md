---
title: __raise
description: ネイティブイベント処理に Microsoft C++ extension キーワードを使用する方法につい `__raise` て説明します。
ms.date: 11/20/2020
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.openlocfilehash: c9df602803062bc51b8c0cee13f17263cdc91786
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483149"
---
# <a name="__raise-keyword"></a>`__raise` キーワード

イベントの呼び出しサイトを強調します。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>Syntax

> **`__raise`** *`method-declarator`* **`;`**

## <a name="remarks"></a>注釈

マネージコードからイベントを発生させることができるのは、そのイベントが定義されているクラス内からだけです。 詳細については、[`event`](../extensions/event-cpp-component-extensions.md) をご覧ください。

以外の **`__raise`** イベントを呼び出すと、キーワードによってエラーが生成されます。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)\
[イベント処理](../cpp/event-handling.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[.NET および UWP 用のコンポーネント拡張](../extensions/component-extensions-for-runtime-platforms.md)
