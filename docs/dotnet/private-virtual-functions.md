---
title: プライベート仮想関数 |Microsoft Docs
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
ms.openlocfilehash: 0058d023268fa4d9ca5abe802ff45856e9855dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418074"
---
# <a name="private-virtual-functions"></a>プライベート仮想関数

派生クラスにプライベート仮想関数の処理方法は、Visual c の C++ マネージ拡張から変更されました。

マネージ拡張で、仮想関数のアクセス レベルは、派生クラス内でオーバーライドするには、その機能を制限しません。 新しい構文では、仮想関数はアクセスできない基底クラスの仮想関数をオーバーライドできません。 例えば:

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

この種の設計を新しい構文の実際のマッピングはありません。 基本クラスのメンバー アクセスできるようにするには、プライベートでない 1 つだけですが。 継承されたメソッドは、同じアクセスを持つ必要はありません。 この例では、影響を最小限変更 MyBaseClass メンバーにするのには`protected`します。 この方法 MyBaseClass を通じてメソッドへの一般的なプログラムのアクセスが禁止されたままです。

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

なお、休暇の明示的な`virtual`新しい構文では、基本クラスのキーワードには、警告メッセージが生成されます。

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
