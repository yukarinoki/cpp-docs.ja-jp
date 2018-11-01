---
title: __raise
ms.date: 11/04/2016
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
ms.openlocfilehash: 865524fe91b7d137e3a943973dcca6d833bd16df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471436"
---
# <a name="raise"></a>__raise

イベントの呼び出しサイトを強調します。

## <a name="syntax"></a>構文

```
__raise method-declarator;
```

## <a name="remarks"></a>Remarks

マネージド コードからは、イベントが定義されたクラス内からのみイベントを発生させることができます。 参照してください[イベント](../windows/event-cpp-component-extensions.md)詳細についてはします。

キーワード **_ _raise**非イベントを呼び出す場合に生成されるエラーが発生します。

> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。

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

[キーワード](../cpp/keywords-cpp.md)<br/>
[イベント処理](../cpp/event-handling.md)<br/>
[ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)