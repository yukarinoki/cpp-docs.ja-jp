---
title: コンス トラクターの初期化の順序の変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors, C++
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd54e9810131f3ddfabe458c70ddef081568a9cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397690"
---
# <a name="changes-in-constructor-initialization-order"></a>コンストラクターの初期化処理の順序における変更

クラスのコンス トラクターの初期化の順序は、Visual c の C++ マネージ拡張から変更されました。

## <a name="comparison-of-constructor-initialization-order"></a>コンス トラクターの初期化の順序の比較

C++ マネージ拡張では、コンス トラクターの初期化は、次の順序で発生しました。

1. 基本クラスのコンス トラクターする場合に呼び出されます。

1. クラスの初期化リストが評価されます。

1. クラス コンス トラクターのコード本体が実行されます。

この実行の順序では、ネイティブの C++ プログラミングのように同じ規則に従います。 新しい Visual C 言語では、CLR クラスの次の実行順序は規定します。

1. クラスの初期化リストが評価されます。

1. 基本クラスのコンス トラクターする場合に呼び出されます。

1. クラス コンス トラクターのコード本体が実行されます。

この変更は CLR クラスにのみ適用されます。Visual C でのネイティブ クラスには、前の規則がまだに従います。 どちらの場合も、これらの規則は、特定のクラス階層全体のチェーン全体で上に伝播します。

C++ マネージ拡張を使用して、次のコード例を検討してください。

```
__gc class A
{
public:
   A() : _n(1)
   {
   }

protected:
   int _n;
};

__gc class B : public A
{
public:
   B() : _m(_n)
   {
   }
private:
   int _m;
};
```

前述したコンス トラクターの初期化の順序に従うと、次の順序の実行時に新しいことを確認クラスのインスタンス`B`構築されます。

1. 基底クラスのコンス トラクター`A`が呼び出されます。 `_n`にメンバーが初期化される`1`します。

1. クラスの初期化リスト`B`が評価されます。 `_m`にメンバーが初期化される`1`します。

1. クラスのコード本体`B`を実行します。

新しい Visual C 構文で同じコードについて考えてみましょう。

```
ref class A
{
public:
   A() : _n(1)
   {
   }

protected:
   int _n;
};

ref class B : A
{
public:
   B() : _m(_n)
   {
   }
private:
   int _m;
};
```

実行時に新しい順序クラスのインスタンス`B`構築されているか、新しい構文は。

1. クラスの初期化リスト`B`が評価されます。 `_m`にメンバーが初期化される`0`(`0`の初期化されていない値である、`_m`クラスのメンバー)。

1. 基底クラスのコンス トラクター`A`が呼び出されます。 `_n`にメンバーが初期化される`1`します。

1. クラスのコード本体`B`を実行します。

同様の構文にこれらのコード例の異なる結果が生成されることに注意してください。 クラスのコンス トラクター`B`基底クラスからの値に依存`A`をそのメンバーを初期化します。 ただし、クラスのコンス トラクター`A`まだ呼び出されています。 このような依存関係は、継承されたクラスが基底クラスのコンス トラクターで発生するメモリまたはリソースの割り当てに依存する場合、特に危険なことができます。

## <a name="what-this-means-going-from-managed-extensions-for-c-to-visual-c-2010"></a>マネージ拡張から Visual C 2010 の c++ とどのような意味

多くの場合クラスのコンス トラクターの実行順序の変更に対して透過的になります、プログラマの基本クラスで継承するクラスの動作の概念がないためです。 ただし、これらのコード例に示すよう継承するクラスのコンス トラクターが大幅に影響が、初期化リストを基底クラスのメンバーの値に依存している場合。 移動を検討する新しい構文で、c++ マネージ拡張からコードを移動するときに実行が保証されているクラスのコンス トラクターの本体にこのような構造が最後に発生します。

## <a name="see-also"></a>関連項目

[マネージ型 (C +/cli CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[コンストラクター](../cpp/constructors-cpp.md)
