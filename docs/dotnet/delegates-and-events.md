---
title: デリゲートとイベント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- delegate keyword [C++]
- delegates [C++], upgrading from Managed Extensions for C++
- __delegate keyword
- events [C++], upgrading from Managed Extensions for C++
- event keyword [C++]
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 26b67cdce8d52cba7d02f182f0582e20d0303c33
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373309"
---
# <a name="delegates-and-events"></a>デリゲートとイベント

デリゲートとイベントを宣言する方法は、Visual c の C++ マネージ拡張から変更されました。

二重のアンダー スコアは必要がなくなったら、次の例に示すようにします。 マネージ拡張のサンプル コードを次に示します。

```
__delegate void ClickEventHandler(int, double);
__delegate void DblClickEventHandler(String*);

__gc class EventSource {
   __event ClickEventHandler* OnClick;
   __event DblClickEventHandler* OnDblClick;
};
```

新しい構文で同じコードは次のようになります。

```
delegate void ClickEventHandler( int, double );
delegate void DblClickEventHandler( String^ );

ref class EventSource {
   event ClickEventHandler^ OnClick;
   event DblClickEventHandler^ OnDblClick;
};
```

イベント (およびデリゲート) は参照型である新しい構文ではオフ、hat を使用するため (`^`)。  イベントは、明示的な宣言の構文と上記のコードに示すように単純な形式の両方をサポートします。 明示的な形式でユーザーを指定します、 `add`、 `raise`、および`remove`イベントに関連付けられているメソッド。 (のみ、`add`と`remove`メソッドが必要です`raise`メソッドは省略可能。)。

マネージ拡張でも、明示的なイベントの宣言を指定しない場合、これらのメソッドを提供するが、存在しないイベントの名前を決定する必要があります。 各メソッドが、フォームで指定された`add_EventName`、 `raise_EventName`、および`remove_EventName`マネージ拡張仕様から引用した次の例のように。

```
// explicit implementations of add, remove, raise
public __delegate void f(int);
public __gc struct E {
   f* _E;
public:
   E() { _E = 0; }

   __event void add_E1(f* d) { _E += d; }

   static void Go() {
      E* pE = new E;
      pE->E1 += new f(pE, &E::handler);
      pE->E1(17);
      pE->E1 -= new f(pE, &E::handler);
      pE->E1(17);
   }

private:
   __event void raise_E1(int i) {
      if (_E)
         _E(i);
   }

protected:
   __event void remove_E1(f* d) {
      _E -= d;
   }
};
```

新しい構文では、次の変換例が示すように、宣言が簡略化します。 3 つのメソッドはかっこで囲まれ、次のように、イベントとその関連付けられているデリゲート型の宣言の直後に配置またはイベントが 2 つを指定します。

```
public delegate void f( int );
public ref struct E {
private:
   f^ _E; // delegates are also reference types

public:
   E() {  // note the replacement of 0 with nullptr!
      _E = nullptr;
   }

   // the new aggregate syntax of an explicit event declaration
   event f^ E1 {
   public:
      void add( f^ d ) {
         _E += d;
      }

   protected:
      void remove( f^ d ) {
         _E -= d;
      }

   private:
      void raise( int i ) {
         if ( _E )
            _E( i );
      }
   }

   static void Go() {
      E^ pE = gcnew E;
      pE->E1 += gcnew f( pE, &E::handler );
      pE->E1( 17 );
      pE->E1 -= gcnew f( pE, &E::handler );
      pE->E1( 17 );
   }
};
```

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[delegate (C++ コンポーネント拡張)](../windows/delegate-cpp-component-extensions.md)<br/>
[event](../windows/event-cpp-component-extensions.md)