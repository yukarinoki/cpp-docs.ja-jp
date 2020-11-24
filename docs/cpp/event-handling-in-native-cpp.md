---
title: ネイティブ C++ でのイベント処理
description: ネイティブ C++ のイベント処理に Microsoft C++ 拡張機能を使用する方法について説明します。
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: 5ad9128b7ff596674c3b08687b722c81b7a10aa8
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483179"
---
# <a name="event-handling-in-native-c"></a>ネイティブ C++ でのイベント処理

ネイティブ C++ のイベント処理では、 [event_source](../windows/attributes/event-source.md)と[event_receiver](../windows/attributes/event-receiver.md)属性を使用して、イベントソースとイベントレシーバーをそれぞれ設定し `type` = `native` ます。 これらの属性は、適用先のクラスを使用して、イベントを発生させ、ネイティブの非 COM コンテキストでイベントを処理します。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="declaring-events"></a>イベントの宣言

イベントソースクラスでは、メソッド [`__event`](../cpp/event.md) 宣言でキーワードを使用して、メソッドをイベントとして宣言します。 必ずメソッドを宣言してください。ただし、定義しないでください。 このようにすると、コンパイラは、イベントが発生したときにメソッドを暗黙的に定義するため、コンパイラエラーが生成されます。 ネイティブ イベントは、ゼロ以上のパラメーターを持つメソッドにできます。 戻り値の型は、または任意の整数型にすることができ **`void`** ます。

## <a name="defining-event-handlers"></a>イベントハンドラーの定義

イベントレシーバークラスでは、イベントハンドラーを定義します。 イベントハンドラーは、処理するイベントに一致するシグネチャ (戻り値の型、呼び出し規則、および引数) を持つメソッドです。

## <a name="hooking-event-handlers-to-events"></a>イベントへのイベントハンドラーのフック

また、イベントレシーバークラスでは、イベントをイベント [`__hook`](../cpp/hook.md) ハンドラーに関連付けたり、イベントハンドラーからイベントの関連付けを解除したりするために、組み込み関数を使用し [`__unhook`](../cpp/unhook.md) ます。 複数のイベントを 1 つのイベント ハンドラーにフックすることも、複数のイベント ハンドラーを 1 つのイベントにフックすることもできます。

## <a name="firing-events"></a>イベントの発生

イベントを発生させるには、イベントソースクラスでイベントとして宣言されたメソッドを呼び出します。 ハンドラーがイベントにフックされている場合は、ハンドラーが呼び出されます。

### <a name="native-c-event-code"></a>ネイティブ C++ イベントコード

次の例は、ネイティブ C++ でイベントを発生させる方法を示しています。 例をコンパイルして実行するには、コード内のコメントを参照してください。 Visual Studio IDE でコードをビルドするには、オプションがオフになっていることを確認し **`/permissive-`** ます。

## <a name="example"></a>例

### <a name="code"></a>コード

```cpp
// evh_native.cpp
// compile by using: cl /EHsc /W3 evh_native.cpp
#include <stdio.h>

[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};

[event_receiver(native)]
class CReceiver {
public:
   void MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
   }

   void MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
   }

   void hookEvent(CSource* pSource) {
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void unhookEvent(CSource* pSource) {
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   CSource source;
   CReceiver receiver;

   receiver.hookEvent(&source);
   __raise source.MyEvent(123);
   receiver.unhookEvent(&source);
}
```

### <a name="output"></a>出力

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>関連項目

[イベント処理](../cpp/event-handling.md)
