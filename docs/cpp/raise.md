---
title: __raise
ms.date: 11/04/2016
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
ms.openlocfilehash: eb3ab24378071663b2a6a1abab700b81c3172419
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317233"
---
# <a name="__raise"></a>__raise

イベントの呼び出しサイトを強調します。

## <a name="syntax"></a>構文

```
__raise method-declarator;
```

## <a name="remarks"></a>解説

マネージド コードからは、イベントが定義されたクラス内からのみイベントを発生させることができます。 詳細については[、イベント](../extensions/event-cpp-component-extensions.md)を参照してください。

キーワード **__raise**を呼び出すと、非イベントを呼び出すとエラーが生成されます。

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

[Keywords](../cpp/keywords-cpp.md)<br/>
[イベント処理](../cpp/event-handling.md)<br/>
[ランタイム プラットフォームのコンポーネントの拡張機能](../extensions/component-extensions-for-runtime-platforms.md)
