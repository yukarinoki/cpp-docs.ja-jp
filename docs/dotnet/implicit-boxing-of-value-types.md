---
title: 値の型の暗黙的なボックス化 |Microsoft ドキュメント
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
ms.openlocfilehash: f1f5a455333e5cb40b63d5a5237b2df053cef194
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132220"
---
# <a name="implicit-boxing-of-value-types"></a>値型の暗黙のボックス化
値型のボックス化は、Visual C を c++ マネージ拡張から変更されました。  
  
 言語設計では、代わりに、機能の実際の経験哲学的な位置が課されることを実際には、それは誤りでした。 比喩で元の複数の継承言語デザイン Stroustrup ことが決定したがって言語必要される仮想ベースとして機能している任意のクラスを派生クラスのコンス トラクター内で、仮想基底クラスの下位のオブジェクトを初期化できませんでした。クラスは、既定のコンス トラクターを定義する必要があります。 後続の仮想派生によって呼び出される既定のコンス トラクターです。  
  
 仮想基本クラスの階層構造の問題は、後続の派生で共有仮想下位のオブジェクトの初期化の責任をシフトすることです。 などの基本クラスを定義した場合どの初期化には、ユーザーが指定したバッファーのサイズをバッファーの割り当てが必要です。 渡されますを引数としてコンス トラクターに。 後続の 2 つの仮想派生提供し場合、呼び出す`inputb`と`outputb`、基底クラス コンス トラクターに特定の値を紹介します。 ここで、私の派生、`in_out`両方からクラスを`inputb`と`outputb`、共有仮想基底クラスの下位のオブジェクトにそれらの値のいずれも十できるようにするを評価します。  
  
 そのため、元の言語設計 Stroustrup には、メンバー初期化リスト内で、派生クラスのコンス トラクターの仮想基底クラスの明示的な初期化が許可されていません。 これには、問題が解決したら、中に実際には、仮想基底クラスの初期化を指示することができない証明実行不可能と判明します。 Nihcl と呼ばれる SmallTalk コレクションのライブラリのフリーウェア バージョンを実装した、ユーザー、National Institute の正常性、Keith Gorlen 程度のより柔軟な言語設計を考案する he ' d Stroustrup 原則音声をでした。  
  
 階層的なデザインのオブジェクト指向の原則は、派生クラスはその直接の基本クラスの非プライベートな実装でのみ自体に関係を保持します。 仮想継承の柔軟な初期化のデザインをサポートするために、Stroustrup は、この原則に違反する必要があります。 階層の最派生クラスでは、発生した階層に詳細な方法に関係なくすべての仮想サブオブジェクト初期化の責任を引き継ぎます。 たとえば、`inputb`と`outputb`が両方とも、即時仮想基底クラスを明示的に初期化を担当します。 ときに`in_out`両方から派生した`inputb`と`outputb`、`in_out`になった 1 回のみの初期化が仮想基底クラスを削除し、内で明示的に初期化が行われます`inputb`と`outputb`は抑制されます。  
  
 これは、言語の開発者によってが複雑なセマンティクスを必要な柔軟性を提供します。 コンプリケーションのこの負担は取り除かれます仮想基本クラスには、状態を含まず、単にインターフェイスを指定することを許可できないようにする場合。 これは、C++ での推奨される設計手法です。 Clr プログラミング、インターフェイス型を持つポリシーにこれが発生します。  
  
 ここでの単純なコード サンプルでは、ここでは、明示的なボックス化する必要はありません。  
  
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
  
 ご覧のように、多数のボックス化と詳細があります。 Visual C は、値の型のボックス化は暗黙的な。  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## <a name="see-also"></a>関連項目  
 [値の型とその動作 (C + + CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [ボックス化](../windows/boxing-cpp-component-extensions.md)