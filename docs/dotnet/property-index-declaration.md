---
title: プロパティ インデックスの宣言 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- indexers
- default indexers
- defaults, indexers
- indexed properties, C++
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 76473ce04cdf5860476b7612ddcbf00b40a0fae1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33160837"
---
# <a name="property-index-declaration"></a>プロパティ インデックスの宣言
インデックス付きプロパティを宣言する構文は、Visual C を c++ マネージ拡張から変更されました。  
  
 インデックス付きプロパティのマネージ拡張言語のサポートの 2 つの主な欠点は、クラス レベルの添字演算子; を提供することができません。つまり、すべてのインデックス付きプロパティは、名前を指定するために必要、したがって方法はありません、たとえば、直接に適用する管理対象の添字演算子を提供する、`Vector`または`Matrix`クラス オブジェクト。 重大な欠点を以下の 2 番目を視覚的に、インデックス付きプロパティからプロパティを識別するが困難であるパラメーターの数がだけが示されますです。 最後に、インデックス付きプロパティのプロパティのインデックス付きでないものと同じ問題 - アクセサーがない、アトミック単位として扱われますが、個々 のメソッドに分割します。  例えば:  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 インデクサーが、2 つを指定するか、1 つの追加のパラメーターによってのみ区別がわかるようにここで、次元のインデックス。 新しい構文では、インデクサーは、角かっこ ([、]) 次のインデクサーの名前と各インデックスの種類と数を示すによって識別されます。  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 新しい構文では、クラスのオブジェクトに直接適用できるクラス レベルのインデクサーを示すために、`default`キーワードは、明示的な名前の代わりに再利用します。 例えば:  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 新しい構文では、既定のインデックス付きプロパティが指定されて、次の 2 つの名前は予約されています:`get_Item`と`set_Item`です。 これらは、基になる名前、既定のインデックス付きプロパティに対して生成されるためです。  
  
 ない単純なインデックスの構文、単純なプロパティの構文に似ていますに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 