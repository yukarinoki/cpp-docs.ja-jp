---
title: 値型の暗黙的なボックス化 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, Visual C++
- __box keyword
- boxing
- boxing, __box keyword
- value types, boxed
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e9c232dba6d766d0855bb4bb29e33d85b5fd5a2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387589"
---
# <a name="implicit-boxing-of-value-types"></a>値型の暗黙のボックス化

値型のボックス化は、Visual c の C++ マネージ拡張から変更されました。

言語設計において実用的な経験、機能の代わりの哲学的な位置が課せられることと、実際には、間違いが。 類推として元の複数の継承言語設計 Stroustrup 決定そのため、言語の 必要な仮想ベースとして使用される任意のクラスを派生クラスのコンス トラクター内で、仮想基底クラスのサブオブジェクトを初期化できませんでした。クラスは、既定のコンス トラクターを定義する必要があります。 後続の仮想派生によってその既定のコンス トラクターになります。

仮想基底クラスの階層の問題は、後続の派生で共有仮想サブオブジェクトを初期化するための責任をシフトすることです。 たとえばの基本クラスを定義する場合が初期化には、そのバッファーのユーザーが指定したサイズ、バッファーの割り当てが必要です。 可能性があります引数として渡すこと、コンス トラクターにします。 後続の 2 つの仮想派生提供し場合、それらを呼び出す`inputb`と`outputb`、基底クラスのコンス トラクターに特定の値を提供します。 派生したときに、`in_out`両方からクラス`inputb`と`outputb`、共有仮想基底クラスのサブオブジェクトへのそれらの値のどちらを評価する常識的許可できます。

そのため、元の言語設計 Stroustrup には、派生クラスのコンス トラクターの仮想基底クラス メンバーの初期化リスト内の明示的な初期化が許可されていません。 これには、問題が解決したら、中に実際には、仮想基底クラスの初期化を指示することができないことがわかりました実行不可能と判明します。 Nihcl と呼ばれる SmallTalk コレクションのライブラリのフリーウェア版を実装した、ユーザー、National Institute の正常性の Keith Gorlen 程度のより柔軟な言語設計を考え出す必要がある Stroustrup 原則音声が発生しました。

オブジェクト指向の階層設計の原則に従えば派生クラスがその直接の基本クラスの非プライベートな実装でのみ自体に関係します。 仮想継承の柔軟な初期化のデザインをサポートするために、Stroustrup は、この原則に違反する必要があります。 階層の最派生クラスでは、発生した階層に深さに関係なくすべての仮想サブオブジェクト初期化の責任を負います。 たとえば、`inputb`と`outputb`はどちらも、即時の仮想基底クラスを明示的に初期化する責任を負います。 ときに`in_out`両方から派生した`inputb`と`outputb`、 `in_out` 、1 回の初期化が仮想基底クラスを削除し、内で明示的な初期化が行われたの責任になります`inputb`と`outputb`は抑制されます。

これは、言語の開発者が複雑なセマンティクスを必要な柔軟性を提供します。 コンプリケーションのこの負担は取り除かれますと状態を使用しないようにするインターフェイスを指定するには仮想基底クラスは制限がある場合。 これは、C++ での推奨される設計手法です。 Clr プログラミング、これはインターフェイス型を持つポリシーに発生します。

ここでは、単純なコード サンプルとここでは、明示的なボックス化する必要はありません。

```
// Managed Extensions for C++ requires explicit __box operation
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };
Object* myObjArray __gc[] = {
   __box(26), __box(27), __box(28), __box(29), __box(30)
};

Console::WriteLine( "{0}\t{1}\t{2}", __box(0),
   __box(my1DIntArray->GetLowerBound(0)),
   __box(my1DIntArray->GetUpperBound(0)) );
```

ご覧のとおり、多数のボックス化が起こっているがあります。 Visual C は、値の型が暗黙的にボックス化。

```
// new syntax makes boxing implicit
array<int>^ my1DIntArray = {1,2,3,4,5};
array<Object^>^ myObjArray = {26,27,28,29,30};

Console::WriteLine( "{0}\t{1}\t{2}", 0,
   my1DIntArray->GetLowerBound( 0 ),
   my1DIntArray->GetUpperBound( 0 ) );
```

## <a name="see-also"></a>関連項目

[値型とその動作 (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[ボックス化](../windows/boxing-cpp-component-extensions.md)