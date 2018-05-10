---
title: 明示的なインスタンス化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4925a60843ada350a2795709d9257ab796616a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="explicit-instantiation"></a>明示的なインスタンス化
明示的なインスタンス化によって、テンプレート化されたクラスまたは関数をコードで実際に使用することなく、そのインスタンスを作成できます。 配布用のテンプレートを使用するライブラリ (.lib) ファイルを作成する場合は、この方法が便利です。そのため、インスタンス化されないテンプレート定義はオブジェクト (.obj) ファイルに格納されません。  
  
 次のコードは `MyStack` 変数と 6 つの項目に対して明示的に `int` をインスタンス化します。  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 このステートメントは、オブジェクトのためのストレージを予約しないで `MyStack` のインスタンス化を作成します。 コードはすべてのメンバーに対して生成されます。  
  
 次の行はコンストラクター メンバー関数のみを明示的にインスタンス化します。  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 明示的にインスタンス化関数テンプレートを使用して、特定の型引数をそれらを再宣言の例で示すように[関数テンプレートのインスタンス化](../cpp/function-template-instantiation.md)です。  
  
 `extern` キーワードを使用して、メンバーが自動的にインスタンス化されないようにすることができます。 例えば:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 同様に、外部のインスタンス化されていないメンバーとして特定のメンバーを次のようにマークできます。  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 `extern` キーワードを使用して、コンパイル時、複数のオブジェクト モジュールで同じコードがインスタンスされないようにできます。 関数が呼び出される場合には、少なくとも 1 つのリンクされたモジュールで指定した明示的なテンプレート パラメーターを使用して、テンプレート関数をインスタンス化する必要があります。そのようにインスタンス化しないと、プログラムのビルド時にリンカー エラーが発生します。  
  
> [!NOTE]
>  特殊化の `extern` キーワードは、クラス本体の外部で定義されたメンバー関数にのみ適用されます。 クラス宣言内で定義されている関数はインライン関数と見なされ、常にインスタンス化されます。  
  
## <a name="see-also"></a>関連項目  
 [関数テンプレート](../cpp/function-templates.md)