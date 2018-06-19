---
title: トークン連結演算子 (#) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '##'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6e224c0327a7ba50c3e13ca78d749f41ad4641f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842232"
---
# <a name="token-pasting-operator-"></a>トークン連結演算子 (##)
二重シャープ記号つまり"トークン連結演算子 (**##**)、両方のオブジェクトのようなと関数に似たマクロで使用されて、「マージ」演算子と呼ばれることがあります。 この演算子を使用すると、別々のトークンを 1 つのトークンに結合できます。そのため、これをマクロ定義の最初または最後のトークンにすることはできません。  
  
 マクロ定義の仮パラメーターの前または後ろにトークン連結演算子がある場合、仮パラメーターは展開されていない実引数に即座に置き換えられます。 引数に対するマクロ展開が置換の前に行われることはありません。  
  
 次に、発生するたびにトークン連結演算子*トークン文字列*が削除され、前と後に続くトークンが連結されたとします。 結果のトークンは有効なトークンである必要があります。 有効であれば、トークンがスキャンされ、マクロ名を表す場合は置換が可能かどうかが確認されます。 この識別子は、置換前のプログラム内で連結されたトークンを認識するための名前になります。 各トークンは、他のどこか、つまり、プログラム内またはコンパイラのコマンド ラインで定義された特定のトークンを表します。 演算子の前または後の空白は、省略可能です。  
  
 この例は、プログラムの出力を指定するときの、文字列化演算子とトークン連結演算子の両方の使用方法を示しています。  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 マクロが次のような数値引数で呼び出された場合、  
  
```  
paster( 9 );  
```  
  
 このマクロは次のようになり、  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 さらに、次のようになります。  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## <a name="example"></a>例  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)