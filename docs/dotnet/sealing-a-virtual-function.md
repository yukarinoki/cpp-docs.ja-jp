---
title: 仮想関数のシール |Microsoft Docs
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
ms.openlocfilehash: 69ac614d55ade10b94621da2a3eb1c43d25ebaf5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385184"
---
# <a name="sealing-a-virtual-function"></a>仮想関数のシール

仮想関数のシールの構文は、Visual c の C++ マネージ拡張から変更されました。

`__sealed`キーワードは、いずれかの参照型からの後続の派生を禁止することを変更するマネージ拡張で使用されます (を参照してください[マネージ クラス型の宣言](../dotnet/declaration-of-a-managed-class-type.md))、または、仮想関数を変更する許可後続の派生クラスでメソッドのオーバーライド。 例えば:

```
__gc class base { public: virtual void f(); };
__gc class derived : public base {
public:
   __sealed void f();
};
```

この例で`derived::f()`オーバーライド、`base::f()`関数プロトタイプの正確な一致に基づいてインスタンス。 `__sealed`キーワードは派生クラスから継承された後続のクラスがのオーバーライドを提供できませんを示します`derived::f()`します。

新しい構文で`sealed`以前のように、実際の関数プロトタイプの前にどこにでも表示を許可されているのではなく、署名後に置かれます。 さらに、使用`sealed`明示的な使用が必要です、`virtual`キーワードもします。 適切な翻訳`derived`前述のとおりです。

```
ref class derived: public base {
public:
   virtual void f() override sealed;
};
```

ない場合、`virtual`このインスタンスにエラーが発生します。 コンテキスト キーワードの新しい構文では`abstract`の代わりに使用できる、`=0`を純粋仮想関数を示します。 これは、マネージ拡張でサポートされていません。 例えば:

```
__gc class base { public: virtual void f()=0; };
```

として書き直すことができます。

```
ref class base { public: virtual void f() abstract; };
```

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[sealed](../windows/sealed-cpp-component-extensions.md)