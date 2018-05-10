---
title: デリゲートおよびイベント |Microsoft ドキュメント
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
ms.openlocfilehash: 69e0ffcb9b9c48de152a383b4b9a3f6edbe99f42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="delegates-and-events"></a>デリゲートとイベント
デリゲートおよびイベントを宣言するための方法は、Visual C を c++ マネージ拡張から変更されました。  
  
 二重のアンダー スコアが不要になった、次の例に示すようにします。 ここでは、マネージ拡張のサンプル コード:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 新しい構文では、同じコードは次のようになります。  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 イベント (およびデリゲート) が参照型で、これは新しい構文ではオフ、hat を使用するため (`^`)。  イベントは、明示的な宣言構文と上記のコードに示すように単純な形式の両方をサポートします。 明示的な形式でユーザーを指定します、 `add`、 `raise`、および`remove`イベントに関連付けられたメソッドです。 (だけ、`add`と`remove`メソッドが必要で;`raise`メソッドは省略可能)。  
  
 マネージ拡張では、これらのメソッドを提供する場合も、明示的なイベントの宣言を指定しないが、存在しないイベントの名前にする必要があります。 各メソッドは、フォームで指定された`add_EventName`、 `raise_EventName`、および`remove_EventName`マネージ拡張の仕様から引用した次の例のように。  
  
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
  
 新しい構文では、次の変換例が示すように、宣言が簡略化します。 3 つのメソッドが中かっこで囲むし、次に示すように、イベントとその関連するデリゲート型の宣言の直後に配置またはイベントが、2 つを指定します。  
  
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
 [クラスまたはインターフェイス内でメンバーの宣言 (C + + CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [delegate (C++ コンポーネント拡張)](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)