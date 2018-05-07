---
title: プロパティ宣言 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bc2cf76384078e579756abe653fb45fd1e97707f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="property-declaration"></a>プロパティの宣言
マネージ クラスのプロパティを宣言するための方法は、Visual C を c++ マネージ拡張から変更されました。  
  
 マネージ拡張でデザインする場合に、各`set`または`get`プロパティ アクセサーは独立した手段として指定します。 各メソッドの宣言が付いて、`__property`キーワード。 メソッド名がいずれかで始まる`set_`または`get_`(としてユーザーに表示) プロパティの実際の名前が続きます。 したがって、`Vector`を提供する、`x`調整`get`プロパティと名前を付けます`get_x`し、ユーザーは、としては起動`x`です。 この名前付け規則とメソッドの別の仕様は実際にはプロパティの基になるランタイムの実装を反映します。 たとえば、ここでは、`Vector`で一連の座標のプロパティ。  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 これは、プロパティに関連付けられている機能外へ広がるし、構文的に関連付けられている設定と取得を統一する必要があります。 さらに、詳細です。 C# の場合と同様により、新しい構文では、`property`キーワードの後に、プロパティと非装飾名の型。 `set`と`get`アクセス メソッドは、プロパティ名に続くブロック内に配置します。 異なり、C# の場合は、アクセス メソッドのシグネチャが指定されていることを注意してください。 たとえば、新しい構文に変換上記のコード例を次に示します。  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 プロパティのアクセス方法がなど異なるアクセス レベルを反映するかどうか、`public get`と`private`または`protected set`、明示的なアクセス権ラベルを指定することができます。 既定では、プロパティのアクセス レベルには、外側のアクセス レベルが反映されます。 たとえば、上記の定義で`Vector`の両方を`get`と`set`メソッドは`public`します。 させる、`set`メソッド`protected`または`private`定義を次のように改訂は。  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 プロパティ内でアクセス キーワードのスコープは、プロパティの右中かっこまたは追加のアクセス キーワードが指定されるまで拡張します。 プロパティが定義されている外側外側のアクセス レベルは、プロパティの定義を超えるは拡張されません。 たとえば、上記の宣言で`Vector::dot()`パブリック メソッドします。  
  
 3 つの設定/取得するプロパティの書き込み`Vector`座標 3 つの手順します。  
  
1.  適切な型のプライベート状態のメンバーを宣言します。  
  
2.  ユーザーがその値を取得するときに、それを返します。  
  
3.  新しい値を割り当てます。  
  
 新しい構文で、プロパティの省略構文では使用可能なこの使用状況パターンを自動化します。  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 プロパティの省略構文の重要な副作用は、backstage 状態のメンバーは、コンパイラによって生成、されていないことを除く設定/取得アクセサーでは、関連するクラス内でアクセス可能です。  
  
## <a name="see-also"></a>関連項目  
 [クラスまたはインターフェイス内でメンバーの宣言 (C + + CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [プロパティ](../windows/property-cpp-component-extensions.md)