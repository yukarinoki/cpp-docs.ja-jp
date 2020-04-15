---
title: 継承キーワード
ms.date: 11/04/2016
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
ms.openlocfilehash: f0aae655540b4d3f9130d9840d77e0abcf270cc2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374096"
---
# <a name="inheritance-keywords"></a>継承キーワード

**マイクロソフト固有**

```
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;
```

各値の説明:

*クラス名*<br/>
宣言するクラスの名前。

C++ では、クラスを定義する前にクラス メンバーへのポインターを宣言できます。 次に例を示します。

```cpp
class S;
int S::*p;
```

上記のコードでは、`p`クラス S の整数メンバへのポインタとして宣言されています。ただし、`class S`このコードではまだ定義されていません。宣言されているだけです。 コンパイラがこのようなポインターを検出した場合、そのポインターの汎化表現を作成する必要があります。 この表現のサイズは、指定した継承モデルによって異なります。 コンパイラに継承モデルを指定するには 4 つの方法があります。

- メンバー**へのポインター表現の下の**IDE で

- コマンド ラインで[/vmg](../build/reference/vmb-vmg-representation-method.md)スイッチを使用する

- [pointers_to_members](../preprocessor/pointers-to-members.md)プラグマの使用

- 継承キーワード __single_inheritance **、** **__multiple_inheritance**、および **__virtual_inheritance**を使用します。 この手法により、クラス単位で継承モデルを制御します。

    > [!NOTE]
    >  常にクラスを定義した後で、そのクラスのメンバーへのポインターを宣言する場合は、これらのオプションを使用する必要がありません。

クラスを定義する前に、そのクラスのメンバーへのポインターを宣言すると、作成される実行可能ファイルのサイズと速度に影響を与えます。 クラスで使用する継承が複雑になるほど、そのクラスのメンバーへのポインターを表すために必要なバイト数が多くなります。したがって、そのポインターの解釈に必要なコードも大きくなります。 単一継承は最も簡素で、仮想継承は最も複雑です。

上記の例を次のように変更します。

```cpp
class __single_inheritance S;
int S::*p;
```

この場合、コマンド ライン オプションやプラグマに関係なく、`class S` のメンバーへのポインターは最小サイズの表現を使用します。

> [!NOTE]
> メンバーへのクラス ポインター表現の同じ前方宣言は、そのクラスのメンバーへのポインターを宣言する各翻訳単位で発生する必要があり、その宣言はメンバーへのポインターを宣言する前に発生する必要があります。

以前のバージョンとの互換性を保つには、 **_single_inheritance**、 **_multiple_inheritance**、および **_virtual_inheritance**は、コンパイラ オプション[/Za\(の言語拡張を無効](../build/reference/za-ze-disable-language-extensions.md)にする) が指定されていない限り、 **__single_inheritance**、 **__multiple_inheritance**、**および __virtual_inheritance**の同義語です。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)
