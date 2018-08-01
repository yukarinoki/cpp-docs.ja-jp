---
title: 継承キーワード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cadeefc9ec150aedcb99f1ed531a3478aecfce89
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408415"
---
# <a name="inheritance-keywords"></a>継承キーワード
**Microsoft 固有の仕様**  
  
```  
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;  
```  
  
 それぞれの文字について以下に説明します。  
  
 *クラス名*  
 宣言するクラスの名前。  
  
 C++ では、クラスを定義する前にクラス メンバーへのポインターを宣言できます。 例えば:  
  
```cpp 
class S;  
int S::*p;  
```  
  
 上記のコードで`p`クラス S. の整数メンバーへのポインターとして宣言されますただし、`class S`が宣言されているだけです。 このコードで定義されていません。 コンパイラがこのようなポインターを検出した場合、そのポインターの汎化表現を作成する必要があります。 この表現のサイズは、指定した継承モデルによって異なります。 コンパイラに継承モデルを指定するには 4 つの方法があります。  
  
-   Ide の**メンバーへのポインター表現**  
  
-   使用して、コマンドラインで、 [/vmg](../build/reference/vmb-vmg-representation-method.md)スイッチ  
  
-   使用して、 [pointers_to_members](../preprocessor/pointers-to-members.md)プラグマ  
  
-   継承キーワードを使用して **_ _single_inheritance**、 **_ _multiple_inheritance**、および **_ _virtual_inheritance**します。 この手法により、クラス単位で継承モデルを制御します。  
  
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
>  メンバーへのクラス ポインター表現の同じ前方宣言は、そのクラスのメンバーへのポインターを宣言する各翻訳単位で発生する必要があり、その宣言はメンバーへのポインターを宣言する前に発生する必要があります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)