---
title: 共用体の宣言 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unions
- union keyword [C], declarations
- variant records
ms.assetid: 978c6165-e0ae-4196-afa7-6d94e24f62f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8c52752c1e05cb3c9f2b18a827fb493ba503ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391179"
---
# <a name="union-declarations"></a>共用体の宣言
"共有体宣言" は、一連の変数の値、および共有体に名前を付けるタグ (オプション) を指定します。 変数の値は共用体の "メンバー" と呼ばれ、異なる型を指定できます。 共有体は他の言語における "バリアント レコード" に似ています。  
  
## <a name="syntax"></a>構文  
 *struct-or-union-specifier*:  
 *struct-or-union identifier* opt **{** *struct-declaration-list* **}**  
  
 *struct-or-union identifier*  
  
 *struct-or-union*:  
 **struct**  
  
 **union**  
  
 *struct-declaration-list*:  
 *struct-declaration*  
  
 *struct-declaration-list struct-declaration*  
  
 共用体の内容は、次のように定義されます  
  
 *struct-declaration*:  
 *specifier-qualifier-list struct-declarator-list*  **;**  
  
 *specifier-qualifier-list*:  
 *type-specifier specifier-qualifier-list* opt  
  
 *type-qualifier specifier-qualifier-list* opt  
  
 *struct-declarator-list*:  
 *struct-declarator*  
  
 *struct-declarator-list*  **,**  *struct-declarator*  
  
 **union** の型の変数は、その型で定義されている値のいずれか 1 つを保存します。 同じ規則が構造体と共有体の宣言を制御します。 共有体には、ビット フィールドも設定できます。  
  
 共有体のメンバーは不完全な型、`void` 型、または関数型を持つことができません。 したがって、メンバーを共用体のインスタンスにすることはできませんが、宣言されている共用体型へのポインターにすることはできます。  
  
 共有体型宣言は、テンプレートだけです。 メモリは、変数が宣言されるまで予約されません。  
  
> [!NOTE]
>  2 の型の 1 つの共用体が宣言され、一方の値が格納されていても、もう一方の型で共用体にアクセスできる場合、結果は信頼できません。 たとえば、**float** と `int` の共用体が宣言されます。 **float** 値が保存されますが、プログラムは `int` として値にアクセスします。 このような場合、値は **float** 値の内部ストレージによって異なります。 整数値は信頼できません。  
  
## <a name="examples"></a>例  
 共用体の例を次に示します。  
  
```  
union sign   /* A definition and a declaration */  
{  
    int svar;  
    unsigned uvar;  
} number;  
```  
  
 この例では、`sign` 型の共有体変数を定義し、2 つのメンバー (符号付き整数の `number` および符号なし整数の `svar`) を持つ `uvar` という名前の変数を宣言します。 この宣言によって、`number` の現在の値を、符号付きまたは符号なしの値として保存できるようになります。 この共有体に関連付けられているタグは `sign` です。  
  
```  
union               /* Defines a two-dimensional */  
{                   /*  array named screen */  
    struct      
    {   
      unsigned int icon : 8;    
      unsigned color : 4;  
    } window1;  
    int screenval;  
} screen[25][80];  
```  
  
 `screen` 配列には 2,000 の要素が含まれます。 配列の各要素は、2 つのメンバー `window1` と `screenval` を持つ個別の共用体です。 `window1` メンバーは、2 つのビット フィールド メンバー (`icon` と `color`) を持つ構造体です。 `screenval` メンバーは `int` です。 常に、各共用体の要素は `int` によって表される `screenval` か `window1` によって表される構造体を保持します。  
  
 **Microsoft 固有の仕様**  
  
 入れ子になった共有体は、別の構造体または共用体のメンバーであるとき匿名で宣言できます。 無名の共用体の例を次に示します。  
  
```  
struct str  
{  
    int a, b;  
    union            / * Unnamed union */  
    {  
      char c[4];  
      long l;  
      float f;  
   };  
   char c_array[10];  
} my_str;  
.  
.  
.  
my_str.l == 0L;  /* A reference to a field in the my_str union */  
```  
  
 共有体は、多くの場合、特定の時間に共有体に含まれるデータの型を指定するフィールドを含む構造体の中に入れ子になっています。 これは、このような共用体の宣言の例です。  
  
```  
struct x  
{  
    int type_tag;  
    union  
    {  
      int x;  
      float y;  
    }  
}  
```  
  
 共有体の参照については、「[構造体メンバーと共用体メンバー](../c-language/structure-and-union-members.md)」を参照してください。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [宣言子と変数宣言](../c-language/declarators-and-variable-declarations.md)