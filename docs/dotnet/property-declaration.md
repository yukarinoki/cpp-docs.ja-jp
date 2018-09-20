---
title: プロパティの宣言 |Microsoft Docs
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
ms.openlocfilehash: 019b8eae17952bfe53fd8fbf14db4bafce1bf463
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438302"
---
# <a name="property-declaration"></a>プロパティの宣言

マネージ クラスのプロパティを宣言する方法は、Visual c の C++ マネージ拡張から変更されました。

マネージ拡張で設計する場合に、各`set`または`get`プロパティ アクセサーは独立した手段として指定します。 各メソッドの宣言が付いて、`__property`キーワード。 メソッド名がいずれかで始まる`set_`または`get_`後に (ユーザーに表示) としてプロパティの実際の名前。 つまり、`Vector`を提供する、`x`調整`get`プロパティで名前が`get_x`、ユーザーは、としては起動と`x`。 この名前付け規則とメソッドの別の仕様、プロパティの基になるランタイム実装が実際に反映されます。 たとえば、ここでは、`Vector`で一連の座標のプロパティ。

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

これは、プロパティに関連付けられている機能に分散され、関連付けセットと取得を構文的に統一する必要があります。 さらに、詳細なは。 C# のような詳細については、新しい構文で、`property`キーワードに続けて、プロパティとその修飾名の型。 `set`と`get`アクセス メソッドは、プロパティ名に続くブロック内に配置されます。 異なり、C# の場合、アクセス メソッドのシグネチャが指定されているに注意してください。 たとえば、上記のコード例を新しい構文に変換されます。 次に示します。

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

プロパティのアクセス方法がなど個別のアクセス レベルを反映するかどうか、`public get`と`private`または`protected set`、明示的なアクセス権のラベルを指定できます。 既定では、プロパティのアクセス レベルには、外側のアクセス レベルが反映されます。 たとえば、上記の定義で`Vector`の両方を`get`と`set`メソッドは`public`します。 させる、`set`メソッド`protected`または`private`定義を次のように変更は。

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

プロパティ内のアクセス キーワードのスコープは、プロパティの右中かっこまたは追加のアクセス キーワードが指定されるまで拡張します。 プロパティの定義を外側のアクセス レベルは、プロパティの定義を超えるは拡張されません。 たとえば、上記の宣言で`Vector::dot()`パブリック メソッドします。

3 つの設定/取得するプロパティを書き込む`Vector`座標が 3 つの手順が含まれます。

1. 適切な型のプライベート状態のメンバーを宣言します。

1. ユーザーがその値を取得する必要がある場合は、それを返します。

1. 新しい値を割り当てます。

新しい構文で、プロパティの省略構文では使用可能なこの使用パターンを自動化します。

```
public ref class Vector sealed {
public:
   // equivalent shorthand property syntax
   property double x;
   property double y;
   property double z;
};
```

プロパティの省略構文の興味深い副作用は、backstage の state メンバーは、コンパイラによって生成にはできませんの設定/取得アクセサーを使用してを除き、クラス内でアクセスできます。

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[プロパティ](../windows/property-cpp-component-extensions.md)