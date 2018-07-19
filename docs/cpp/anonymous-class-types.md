---
title: 匿名クラス型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49149a055f60cb24c6f676b91a2d9ddd55132a3a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943917"
---
# <a name="anonymous-class-types"></a>匿名クラス型
クラスを匿名にすることができます: 宣言することがなくこれは、*識別子*します。 クラス名を置き換えるときに便利ですが、 **typedef**次のように、名前。  
  
```cpp 
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
> [!NOTE]
>  前の例で示した匿名クラスの使用は、既存の C コードとの互換性を維持するために役立ちます。 一部の C コードでの使用で**typedef**匿名構造体と組み合わせては普及しています。  
  
 匿名クラスは、次のように、クラス メンバーへの参照が別のクラスに含まれていないかのように見せる場合にも役立ちます。  
  
```cpp 
struct PTValue  
{  
    POINT ptLoc;  
    union  
    {  
        int  iValue;  
        long lValue;  
    };  
};  
  
PTValue ptv;  
```  
  
 上記のコードで`iValue`オブジェクトのメンバー選択演算子を使用してアクセスできます (**.**) 次のようにします。  
  
```cpp 
int i = ptv.iValue;  
```  
  
 匿名クラスには、特定の制限が適用されます  (無名共用体の詳細については、次を参照してください[共用体](../cpp/unions.md)。)。匿名クラスの制限は次のとおりです。  
  
-   コンストラクターやデストラクターを持つことはできません。  
  
-   型チェックが省略記号を使用して無効化されていない限り、関数に引数として渡すことはできません。  
  
-   関数の戻り値として返すことはできません。  
  
## <a name="anonymous-structs"></a>匿名構造体  
  
### <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Microsoft の C 拡張機能を使用すれば、名前を指定せずに、別の構造体内に構造体変数を宣言できます。 このような入れ子の構造体を "匿名構造体" といいます。 C++ では匿名構造体を使用できません。  
  
 匿名構造体のメンバーには、包含構造体のメンバーと同じようにアクセスできます。  
  
```cpp 
// anonymous_structures.c  
#include <stdio.h>  
  
struct phone  
{  
    int  areacode;  
    long number;  
};  
  
struct person  
{  
    char   name[30];  
    char   gender;  
    int    age;  
    int    weight;  
    struct phone;    // Anonymous structure; no name needed  
} Jim;  
  
int main()  
{  
    Jim.number = 1234567;  
    printf_s("%d\n", Jim.number);     
}  
//Output: 1234567  
```  
  
**Microsoft 固有の仕様はここまで**  
  
