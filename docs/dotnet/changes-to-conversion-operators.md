---
title: 変換演算子の変更 |Microsoft ドキュメント
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
ms.openlocfilehash: 750d16bc6fee86d8a3f8b912cdc4c251221dffb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110873"
---
# <a name="changes-to-conversion-operators"></a>変換演算子に対する変更点
変換演算子の構文は、Visual C を c++ マネージ拡張から変更されました。  
  
 1 つの例は、記述する`op_Implicit`変換を指定します。 定義をここでは`MyDouble`言語仕様から取得します。  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 これは、コードは、整数、その整数に変換するためのアルゴリズムが指定された、`MyDouble`によって提供される、`op_Implicit`演算子。 さらに、その変換は、コンパイラによって暗黙的に実行します。 同様に、指定された、`MyDouble`オブジェクト、2 つ`op_Explicit`演算子は、そのオブジェクトに変換する整数値またはマネージのいずれかのそれぞれのアルゴリズムを使用する`String`エンティティです。 ただし、ユーザーによって明示的に要求されない限り、コンパイラは、変換を実行できません。  
  
 C# の場合、この次のとおり。  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 C# コードは、C++ マネージ拡張のバージョンよりも C++ と同様により検索します。 新しい構文ではありません。  
  
 ISO C 委員会に導入されたキーワード、 `explicit`、- などの予想外の結果を軽減するために、`Array`ディメンションは任意の整数を暗黙的に変換すると、1 つの整数の引数をクラス、`Array`オブジェクトを必要ありません。 これを防止する方法の 1 つはコンス トラクターの 2 番目の引数がダミーのデザインの手法  
  
 その一方で、C++ でのクラス型の設計する場合変換ペアを指定しないで必要があります。 そのための最適な例は、標準文字列クラスです。 暗黙的な変換は、C スタイルの文字列を受け取るコンス トラクターを単一の引数です。 ただし、これは提供されませんが、文字列に変換するオブジェクトを C スタイルの文字列ではなく、ユーザーに明示的に名前付き関数でこのケースを呼び出す必要がありますの対応する暗黙的な変換演算子`c_str()`です。  
  
 そのため、変換演算子 (および宣言の 1 つのフォームへの変換のセットをカプセル化として)、暗黙的または明示的な動作を関連付けることがある、に最終的に至った変換演算子の元のC++のサポートの改善`explicit`キーワード。 変換演算子の Visual C の言語サポート次のよう、c# の場合よりも若干簡略化、変換アルゴリズムの暗黙のアプリケーションをサポートする演算子の既定の動作のためには。  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 別の変更は、引数を 1 つのコンス トラクターとして宣言されているかのように処理する`explicit`です。 これは、その呼び出しをトリガーするために、明示的なキャストが必要であることを意味します。 ただし、明示的な変換演算子が定義されている場合と、単一の引数を持つコンス トラクター、されませんが呼び出されることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)