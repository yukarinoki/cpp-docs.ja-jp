---
title: 変換演算子に対する変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- conversion operators
- operators [C++], explicit type conversion
- type conversion, explicit conversions
- conversions, explicit
- explicit keyword [C++]
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03b17c5abc559289a9f85a10b9c5914b49498922
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381115"
---
# <a name="changes-to-conversion-operators"></a>変換演算子に対する変更点

変換演算子の構文は、Visual c の C++ マネージ拡張から変更されました。

1 つの例は、記述する`op_Implicit`への変換を指定します。 定義をここでは`MyDouble`言語仕様から取得されます。

```
__gc struct MyDouble {
   static MyDouble* op_Implicit( int i );
   static int op_Explicit( MyDouble* val );
   static String* op_Explicit( MyDouble* val );
};
```

これは、コードは、整数、整数に変換するためのアルゴリズムを指定する、`MyDouble`によって提供される、`op_Implicit`演算子。 さらに、その変換は、コンパイラによって暗黙的に実行します。 同様に、指定された、`MyDouble`オブジェクト、2 つ`op_Explicit`演算子は、整数またはマネージのいずれかにそのオブジェクトに変換するそれぞれのアルゴリズムを提供する`String`エンティティ。 ただし、ユーザーが明示的に要求されない限り、コンパイラは変換を実行できません。

C# の場合は、このようになります。

```
class MyDouble {
   public static implicit operator MyDouble( int i );
   public static explicit operator int( MyDouble val );
   public static explicit operator string( MyDouble val );
};
```

C# コードは、C++ マネージ拡張よりも C++ のようなより検索します。 新しい構文ではそうではありません。

ISO C 委員会に導入されたキーワード、 `explicit`、予想外の結果 - たとえば、軽減するために、`Array`クラスは、ディメンションは任意の整数に暗黙的に変換すると、1 つの整数の引数、`Array`オブジェクトを必要ありません。 これを回避する方法の 1 つは、コンス トラクターの 2 番目の引数がダミーのデザイン手法です。

その一方で、c++ のクラス型を設計するときに変換ペアを提供しない必要があります。 そのための最適な例は、標準文字列クラスです。 暗黙的な変換は、C スタイル文字列を受け取る引数が 1 つのコンス トラクターです。 ただし、これは提供されませんが、文字列に変換するオブジェクトを C スタイルの文字列ではなく、ユーザーを名前付き関数 - ここを明示的に呼び出す必要がありますの対応する暗黙的な変換演算子`c_str()`します。

そのため、変換演算子 (および宣言の 1 つのフォームへの変換のセットをカプセル化し)、暗黙的/明示的な動作を関連付けることがあります、に最終的に至った変換演算子の元のC++サポートの機能を向上`explicit`キーワード。 変換演算子の Visual C の言語サポートを次にとおり、これは、変換アルゴリズムの暗黙のアプリケーションをサポートしている演算子の既定の動作のための c# よりもわずかに低下詳細です

```
ref struct MyDouble {
public:
   static operator MyDouble^ ( int i );
   static explicit operator int ( MyDouble^ val );
   static explicit operator String^ ( MyDouble^ val );
};
```

として宣言されているかのように、1 つの引数のコンス トラクターを処理する別の変更は、`explicit`します。 これは、その呼び出しをトリガーするには、明示的なキャストが必要であることを意味します。 ただし、明示的な変換演算子が定義されている場合と、引数が 1 つのコンス トラクターされませんが呼び出されることに注意してください。

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)