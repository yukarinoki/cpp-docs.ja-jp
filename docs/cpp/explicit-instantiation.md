---
title: 明示的なインスタンス化
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
ms.openlocfilehash: 0b1290bc23c56c0f35ddd3bb93e37ce4f5f0d2ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361957"
---
# <a name="explicit-instantiation"></a>明示的なインスタンス化

明示的なインスタンス化によって、テンプレート化されたクラスまたは関数をコードで実際に使用することなく、そのインスタンスを作成できます。 配布用のテンプレートを使用するライブラリ (.lib) ファイルを作成する場合は、この方法が便利です。そのため、インスタンス化されないテンプレート定義はオブジェクト (.obj) ファイルに格納されません。

このコードは`MyStack`**、int**変数と 6 つの項目を明示的にインスタンス化します。

```cpp
template class MyStack<int, 6>;
```

このステートメントは、オブジェクトのためのストレージを予約しないで `MyStack` のインスタンス化を作成します。 コードはすべてのメンバーに対して生成されます。

次の行はコンストラクター メンバー関数のみを明示的にインスタンス化します。

```cpp
template MyStack<int, 6>::MyStack( void );
```

関数テンプレートのインスタンス化の例に示すように、特定の型引数を使用して関数[テンプレート](../cpp/function-template-instantiation.md)を明示的にインスタンス化して再宣言できます。

**extern**キーワードを使用すると、メンバーの自動インスタンス化を防ぐことができます。 次に例を示します。

```cpp
extern template class MyStack<int, 6>;
```

同様に、外部のインスタンス化されていないメンバーとして特定のメンバーを次のようにマークできます。

```cpp
extern template MyStack<int, 6>::MyStack( void );
```

**extern**キーワードを使用すると、コンパイラが複数のオブジェクト モジュールで同じインスタンス化コードを生成しないようにすることができます。 関数が呼び出される場合には、少なくとも 1 つのリンクされたモジュールで指定した明示的なテンプレート パラメーターを使用して、テンプレート関数をインスタンス化する必要があります。そのようにインスタンス化しないと、プログラムのビルド時にリンカー エラーが発生します。

> [!NOTE]
> 特殊化の**extern**キーワードは、クラス本体の外部で定義されたメンバー関数にのみ適用されます。 クラス宣言内で定義されている関数はインライン関数と見なされ、常にインスタンス化されます。

## <a name="see-also"></a>関連項目

[関数テンプレート](../cpp/function-templates.md)
