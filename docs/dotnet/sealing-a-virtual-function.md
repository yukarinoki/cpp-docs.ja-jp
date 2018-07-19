---
title: 仮想関数のシール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c85f4775025d3661fdfbf8967b310fb733f452b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164597"
---
# <a name="sealing-a-virtual-function"></a>仮想関数のシール
仮想関数をシールする構文は、Visual C を c++ マネージ拡張から変更されました。  
  
 `__sealed`キーワードは型を変更するか、参照、そこから後続の派生を禁止するマネージ拡張で使用 (を参照してください[マネージ クラス型の宣言](../dotnet/declaration-of-a-managed-class-type.md))、または仮想の関数を変更する許可後続の派生クラスでメソッドのオーバーライドします。 例えば:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 この例では`derived::f()`よりも優先、`base::f()`関数プロトタイプの正確な一致に基づいてインスタンス。 `__sealed`キーワードは、派生クラスから継承された後続のクラスがのオーバーライドを指定できないことを示します`derived::f()`です。  
  
 新しい構文で`sealed`は、実際の関数プロトタイプの前に任意の場所に表示する許可されるのではなく、署名後に置かれます。 さらに、使用する`sealed`、明示的に使用する必要があります、`virtual`キーワードもします。 適切な翻訳`derived`、上記のとおりです。  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 ない場合、`virtual`キーワードがこのインスタンスでエラーが発生します。 新しい構文で、コンテキスト キーワード`abstract`の代わりに使用できる、`=0`純粋仮想関数を示すためにします。 これは、マネージ拡張でサポートされていません。 例えば:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 として書き直すことができます。  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## <a name="see-also"></a>関連項目  
 [クラスまたはインターフェイス内でメンバーの宣言 (C + + CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)