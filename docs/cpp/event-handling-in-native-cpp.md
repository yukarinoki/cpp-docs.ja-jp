---
title: ネイティブ C++ でのイベント処理
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
ms.openlocfilehash: cc9265cd3f9f400e2880405019e4d2c9a934f10a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180083"
---
# <a name="event-handling-in-native-c"></a>ネイティブ C++ でのイベント処理

ネイティブC++イベント処理では、 [event_source](../windows/attributes/event-source.md)と[event_receiver](../windows/attributes/event-receiver.md)属性を使用して、イベントソースとイベントレシーバーをそれぞれ設定し、`type`=`native`を指定します。 これらの属性により、適用先のクラスは、イベントを発生させ、ネイティブの非 COM コンテキストでイベントを処理できます。

## <a name="declaring-events"></a>イベントの宣言

イベントソースクラスでは、メソッド宣言で[__event](../cpp/event.md)キーワードを使用して、メソッドをイベントとして宣言します。 メソッドを宣言する必要がありますが、定義はしないでください。コンパイラは、イベント内でメソッドを暗黙的に定義するため、これを定義した場合、コンパイラ エラーが発生します。 ネイティブ イベントは、ゼロ以上のパラメーターを持つメソッドにできます。 戻り値の型は void または任意の整数型です。

## <a name="defining-event-handlers"></a>イベント ハンドラーの定義

イベント レシーバー クラスでは、イベント ハンドラーを定義します。イベント ハンドラーは、処理するイベントと一致するシグニチャ (戻り値の型、呼び出し規則、引数) を持つメソッドです。

## <a name="hooking-event-handlers-to-events"></a>イベントへのイベント ハンドラーのフック

また、イベントレシーバークラスでは、組み込み関数[__hook](../cpp/hook.md)を使用してイベントをイベントハンドラーに関連付け[__unhook](../cpp/unhook.md)たり、イベントハンドラーからイベントの関連付けを解除したりできます。 複数のイベントを 1 つのイベント ハンドラーにフックすることも、複数のイベント ハンドラーを 1 つのイベントにフックすることもできます。

## <a name="firing-events"></a>イベントの発生

イベントを発生させるには、イベント ソース クラスのイベントとして宣言されたメソッドを呼び出します。 ハンドラーがイベントにフックされている場合は、ハンドラーが呼び出されます。

### <a name="native-c-event-code"></a>ネイティブ C++ イベント コード

次の例は、ネイティブ C++ でイベントを発生させる方法を示しています。 例をコンパイルして実行するには、コード内のコメントを参照してください。

## <a name="example"></a>例

### <a name="code"></a>コード

```cpp
// evh_native.cpp
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

### <a name="output"></a>Output

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>参照

[イベント処理](../cpp/event-handling.md)
