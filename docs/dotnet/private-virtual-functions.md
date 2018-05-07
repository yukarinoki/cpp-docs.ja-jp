---
title: プライベート仮想関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 97b4d7d9f47901fa69aa50bfc6f405355cf378b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="private-virtual-functions"></a>プライベート仮想関数
派生クラスでプライベート仮想関数の処理方法は、Visual C を c++ マネージ拡張から変更されました。  
  
 マネージ拡張で、仮想関数のアクセス レベルは、派生クラス内でオーバーライドされるように機能を制限しません。 新しい構文では、仮想関数はアクセスできない基底クラスの仮想関数をオーバーライドできません。 例えば:  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible  
   void g();  
};  
```  
  
 このような新しい構文にデザインの実際のマッピングはありません。 1 つは、基本クラスのメンバー アクセスできるようにするには、非プライベート単にあります。 継承されたメソッドは、同じアクセス許可に注意する必要はありません。 この例では、影響を最小限の変更が MyBaseClass メンバーにするのには`protected`します。 このように MyBaseClass を通じてメソッドへの一般的なプログラムのアクセスはまだ禁止されています。  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 なおがない場合、明示的な`virtual`新しい構文では、基本クラスのキーワードは、警告メッセージを生成します。  
  
## <a name="see-also"></a>関連項目  
 [クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 