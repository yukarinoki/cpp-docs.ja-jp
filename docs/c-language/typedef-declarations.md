---
title: typedef 宣言 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 192f7ab037362219261852cfdb0a5eac53e5df9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391653"
---
# <a name="typedef-declarations"></a>typedef 宣言
typedef 宣言は、ストレージ クラスとしての typedef による宣言です。 宣言子は、新しい型になります。 typedef 宣言を使用して、既に C で定義されている型や、宣言した型に対して、より短い、またはわかりやすい名前を作成できます。 Typedef 名を使用して、変更可能な実装の詳細をカプセル化できます。  
  
 typedef 宣言は、変数または関数宣言と同様に解釈されますが、宣言によって指定された型を想定する代わりに識別子は型のシノニムになります。  
  
## <a name="syntax"></a>構文  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt **;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*:  
 `typedef`  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 *typedef-name*:  
 *identifier*  
  
 typedef 宣言は型を作成しないことに注意してください。 既存の型のシノニム、またはその他の方法で指定できる型の名前を作成します。 Typedef 名を型指定子として使用するときは、特定の型指定子と組み合わせることはできますが、それ以外とはできません。 使用できる修飾子には **const** と `volatile` が含まれます。  
  
 typedef 名は、通常の識別子を使用して名前空間を共有します (詳細については、「[名前空間](../c-language/name-spaces.md)」を参照してください)。 そのため、プログラムは同じ名前の typedef 名とローカル スコープ識別子を持つことができます。 例:  
  
```  
typedef char FlagType;  
  
int main()  
{  
}  
  
int myproc( int )  
{  
    int FlagType;  
}  
```  
  
 Typedef と同じ名前でローカル スコープの識別子を宣言するとき、あるいは同じスコープまたは内部スコープで構造体または共用体のメンバーを宣言するときは、型指定子を指定する必要があります。 この例では、この制約を示しています。  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 識別子、構造体メンバー、または共用体メンバーに対して `FlagType` 名を再利用するには、次のように型を指定する必要があります。  
  
```  
const int FlagType;  /* Type specifier required */  
```  
  
 次のような記述だけでは不十分です。  
  
```  
const FlagType;      /* Incomplete specification */  
```  
  
 `FlagType` は再宣言された識別子ではなく、型の一部であると見なされるためです。 この宣言は、次のような正しくない宣言であると見なされます。  
  
```  
int;  /* Illegal declaration */  
```  
  
 ポインター、関数、配列型を含め、あらゆる型を typedef で宣言できます。 構造体型または共用体型を定義する前に、構造体型または共用体型へのポインターの typedef 名を宣言できます。ただし、定義が宣言と同じ可視性である必要があります。  
  
 Typedef 名を使用して、コードの読みやすさを向上させることができます。 次の `signal` の宣言 3 つはすべて同じ型を指定します。1 つ目は、typedef 名を使用せずに指定します。  
  
```  
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */  
  
void ( *signal( int, void (*) (int)) ) ( int );  
fv *signal( int, fv * );   /* Uses typedef type */  
pfv signal( int, pfv );    /* Uses typedef type */  
```  
  
## <a name="examples"></a>使用例  
 typedef 宣言の例を次に示します。  
  
```  
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */  
```  
  
 `WHOLE` を `WHOLE i;`、`const WHOLE i;` などの変数宣言で使用できることに注意してください。 ただし、宣言 `long WHOLE i;` は無効です。  
  
```  
typedef struct club   
{  
    char name[30];  
    int size, year;  
} GROUP;  
```  
  
 このステートメントは、3 つのメンバーを持つ構造体の型として `GROUP` を宣言します。 構造体タグ `club` も指定されているため、typedef 名 (`GROUP`) またはその構造体タグを宣言で使用できます。 struct キーワードはタグで使用する必要があります。typedef 名で struct キーワードを使用することはできません。  
  
```  
typedef GROUP *PG; /* Uses the previous typedef name   
                      to declare a pointer            */  
```  
  
 型 `PG` は、構造体型として定義される `GROUP` 型へのポインターとして宣言されています。  
  
```  
typedef void DRAWF( int, int );  
```  
  
 この例は、値を返さず 2 つの int 引数を取る関数に対して、型 `DRAWF` を提供します。 つまり、たとえば、宣言  
  
```  
DRAWF box;   
```  
  
 は、次の宣言と同じです。  
  
```  
void box( int, int );  
```  
  
## <a name="see-also"></a>参照  


