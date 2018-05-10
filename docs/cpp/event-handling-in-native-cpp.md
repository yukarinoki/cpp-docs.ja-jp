---
title: ネイティブ C++ でのイベント処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b233c8329119753e5753e19fd641c6bea5d8e42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="event-handling-in-native-c"></a>ネイティブ C++ でのイベント処理

使用して、イベント ソースとイベント レシーバーを設定するネイティブ C++ イベント処理で、 [event_source](../windows/event-source.md)と[event_receiver](../windows/event-receiver.md)属性にそれぞれを指定する`type` = `native`. これらの属性により、適用先のクラスは、イベントを発生させ、ネイティブの非 COM コンテキストでイベントを処理できます。

## <a name="declaring-events"></a>イベントの宣言

イベント ソース クラスで使用して、 [_ _event](../cpp/event.md)イベントとしてメソッドを宣言するメソッドの宣言でキーワード。 メソッドを宣言する必要がありますが、定義はしないでください。コンパイラは、イベント内でメソッドを暗黙的に定義するため、これを定義した場合、コンパイラ エラーが発生します。 ネイティブ イベントは、ゼロ以上のパラメーターを持つメソッドにできます。 戻り値の型は void または任意の整数型です。  
  
## <a name="defining-event-handlers"></a>イベント ハンドラーの定義

イベント レシーバー クラスでは、イベント ハンドラーを定義します。イベント ハンドラーは、処理するイベントと一致するシグニチャ (戻り値の型、呼び出し規則、引数) を持つメソッドです。  
  
## <a name="hooking-event-handlers-to-events"></a>イベントへのイベント ハンドラーのフック  

組み込み関数を使用する、イベント レシーバー クラスでも[_ _hook](../cpp/hook.md)にイベントをイベント ハンドラーに関連付けると[_ _unhook](../cpp/unhook.md)をイベント ハンドラーからイベントを切り離します。 複数のイベントを 1 つのイベント ハンドラーにフックすることも、複数のイベント ハンドラーを 1 つのイベントにフックすることもできます。  
  
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
  
### <a name="output"></a>出力  
  
```Output
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123.  
```  
  
## <a name="see-also"></a>関連項目

[イベント処理](../cpp/event-handling.md)  

