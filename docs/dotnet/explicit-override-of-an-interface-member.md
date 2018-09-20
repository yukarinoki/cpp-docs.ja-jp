---
title: インターフェイス メンバーの明示的なオーバーライド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57c26c1185eff0e88e18ef23cb8506fb1fed407a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409026"
---
# <a name="explicit-override-of-an-interface-member"></a>インターフェイス メンバーの明示的なオーバーライド

クラス内でインターフェイス メンバーの明示的なオーバーライドを宣言する構文は、Visual c の C++ マネージ拡張から変更されました。

クラス インターフェイスを通じてクラス オブジェクトを使用する場合に使用されると、インターフェイスのハンドル クラスのオブジェクトを操作するときに使用される 1 つのインターフェイスを実装するクラス内でインターフェイス メンバーの 2 つのインスタンスを提供する場合がよくあります。 例えば:

```
public __gc class R : public ICloneable {
   // to be used through ICloneable
   Object* ICloneable::Clone();

   // to be used through an R
   R* Clone();
};
```

マネージ拡張で行うにはこのインターフェイスの名前で修飾メソッドの名前を持つインターフェイス メソッドの明示的な宣言を提供します。 クラスに固有のインスタンスが修飾されていません。 戻り値をキャストする必要はなくなります`Clone`のインスタンスを明示的に呼び出されると、この例では`R`します。

新しい構文で一般的なオーバーライドする機構が導入されています、マネージ拡張構文を置換します。 この例では、次のように書き換えることができます。

```
public ref class R : public ICloneable {
public:
   // to be used through ICloneable
   virtual Object^ InterfaceClone() = ICloneable::Clone;

   // to be used through an R
   virtual R^ Clone();
};
```

このリビジョンでは、明示的にオーバーライドされているインターフェイスのメンバーである必要があります、クラス内で一意の名前を指定します。 ここでは、不適切な名前を紹介した`InterfaceClone`します。 動作が同じままのこれまで、`ICloneable`インターフェイスの名前が変更された呼び出します`InterfaceClone`、型のオブジェクトを使用して、呼び出し中に`R`、2 つ目の起動`Clone`インスタンス。

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[明示的なオーバーライド](../windows/explicit-overrides-cpp-component-extensions.md)