---
title: scanf 関数の文字幅指定 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- scanf
dev_langs:
- C++
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0052f4b270366b2f3aa1e1550f790efcb860597
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="scanf-width-specification"></a>scanf 関数の文字幅指定
この情報は、`scanf_s` など、安全なバージョンを含む `scanf` 関数ファミリの書式指定文字列の解釈に適用されます。 これらの関数は通常、入力ストリームが一連のトークンに分割されていることを前提とします。 トークンは空白 (スペース、タブ、または改行文字) で区切られるか、数値型の場合は数値テキストに変換できない最初の文字による、数値データ型の自然な終了で区切られます。 ただし、幅指定を使用すると、トークンの自然な終了の前に入力の解析が停止することがあります。  
  
 *width* 指定は、`%` と型フィールド指定子 (*width* フィールドと呼ばれる正の整数を含む) との間の文字、およびフィールドのサイズを示す 1 つ以上の文字で構成されます。後者は、整数型が **short** または **long** のどちらであるかを示すなどの、フィールドの型の修飾子ともみなされます。 このような文字はサイズのプレフィックスと呼ばれます。  
  
## <a name="the-width-field"></a>幅フィールド  
 *幅*フィールドは、そのフィールドで読み取られる最大文字数を制御する正の 10 進整数です。 *width* 文字を超える文字は変換されず、対応する `argument` にも格納されません。 空白文字 (スペース、タブ、改行) または指定の書式に応じて変換できない文字がある場合、*width* に達するまでは、*width* より少ない文字が読み取られます。  
  
 幅の指定は、これらの関数 (`scanf_s`、`wscanf_s` など) の安全なバージョンに必要なバッファー サイズ引数とは別に区別されています。 次の例では、幅指定は 20 であり、入力ストリームから 20 文字までが読み取られることを示してます。 バッファー長は 21 であり、入力可能な 20 文字の空きと、null 終端文字が含まれています。  
  
```  
char str[21];  
scanf_s("%20s", str, 21);  
```  
  
 *width* フィールドが使用されていない場合、`scanf_s` はトークン全体をこの文字列に読み取ろうとします。 指定されたサイズがトークン全体に十分でない大きさの場合、コピー先文字列には何も書き込まれません。 *width* フィールドが指定されている場合、トークン内の最初の *width* 文字が null の終端文字と共にコピー先の文字列に書き込まれます。  
  
## <a name="the-size-prefix"></a>サイズ プレフィックス  
 省略可能なプレフィックス **h**、**l**、**ll**、**I64**、**L** は `argument` (変更した型文字に応じて、long または short、1 バイト文字またはワイド文字) のサイズを示しています。 これらの書式指定文字列は、`scanf` または `wscanf` 関数で使用され、次の表に示す引数の解釈を指定します。 型プレフィックス **I64** は Microsoft 拡張機能であり、ANSI とは互換性がありません。 型文字とその意味は、[scanf 関数の型フィールド文字](../c-runtime-library/scanf-type-field-characters.md)の「scanf 関数の型フィールド文字」の表で説明しています。  
  
> [!NOTE]
>  **h**、**l**、および **L** プレフィックスは、`char` データ型で使用する場合は Microsoft の拡張機能です。  
  
### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>scanf および wscanf 書式型指定子のサイズ プレフィックス  
  
|指定する型|プリフィックス|型指定子|  
|----------------|----------------|-------------------------|  
|**double**|**l**|**e**、**E**、**f**、**g**、または **G**|  
|**long double** (double と同じ)|**L**|**e**、**E**、**f**、**g**、または **G**|  
|**long int**|**l**|**d**、**i**、**o**、**x**、または **X**|  
|**long unsigned int**|**l**|**u**|  
|**long long**|**ll**|**d**、**i**、**o**、**x**、または **X**|  
|`short int`|**h**|**d**、**i**、**o**、**x**、または **X**|  
|**short unsigned int**|**h**|**u**|  
|__**int64**|**I64**|**d**、**i**、**o**、**u**、**x**、または **X**|  
|1 バイト文字と `scanf`|**h**|**c** または **C**|  
|1 バイト文字と `wscanf`|**h**|**c** または **C**|  
|ワイド文字と `scanf`|**l**|**c** または **C**|  
|ワイド文字と `wscanf`|**l**|**c** または **C**|  
|1 バイト文字と `scanf`|**h**|**s** または **S**|  
|1 バイト文字と `wscanf`|**h**|**s** または **S**|  
|ワイド文字列と `scanf`|**l**|**s** または **S**|  
|ワイド文字列と `wscanf`|**l**|**s** または **S**|  
  
 次の例では、**h** と **l** を `scanf_s` 関数と `wscanf_s` 関数で使用します:  
  
```  
scanf_s("%ls", &x, 2);     // Read a wide-character string  
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character  
```  
  
 `scanf` ファミリの安全でない関数を使用する場合は、前の引数のバッファー長を示すサイズ パラメーターを省略します。  
  
## <a name="reading-undelimited-strings"></a>区切られていない文字列の読取り  
 空白で区切られていない文字列を読み取るには、角かっこ内の文字セット (**[ ]**) を **s** (文字列) 型の文字に代用できます。 角かっこ内の文字のセットは、制御文字列と呼ばれます。 対応する入力フィールドは、制御文字に表示されない最初の文字まで読み取られます。 セット内の最初の文字がカレット (**^**) の場合、効果は逆になり、入力フィールドは文字セットの残りの部分に表示される最初の文字までが読み取られます。  
  
 **%[a-z]** と **%[z-a]** は **%[abcde...z]** と同等のものと解釈されます。 これは一般的に使われる `scanf` 関数の拡張機能ですが、ANSI 標準では必要とされません。  
  
## <a name="reading-unterminated-strings"></a>未終了の文字列の読み取り  
 終端の null 文字 ('\0') を保存せずに文字列を保存するには、`%`*n***c** を指定します。ここでは *n* は 10 進整数です。 この場合、**c** の型文字は引数が文字配列へのポインターであることを示します。 次の *n* 文字が入力ストリームから指定した場所に読み取られ、null 文字 ('\0') は追加されません。 *n* が指定されていない場合、この既定値は 1 です。  
  
## <a name="when-scanf-stops-reading-a-field"></a>scanf がフィールドの読み取りを停止するタイミング  
 `scanf`関数は文字単位で入力フィールドをスキャンします。 さまざまな理由から、空白文字に達する前に特定のフィールドで読み取りが停止することがあります。  
  
-   指定した幅に到達しました。  
  
-   次の文字を指定のとおり変換できません。  
  
-   次の文字が、一致するはずの制御文字列内の文字と競合しています。  
  
-   次の文字が特定の文字セットに表示されません。  
  
 理由に関係なく、`scanf` 関数が入力フィールドの読み取りを停止すると、次の入力フィールドは、最初の未読文字から始まるとみなされます。 競合する文字がある場合は、それは未読とみなされ、次の入力フィールドの最初の文字、または入力ストリームのそのあとの読み取り操作の最初の文字になります。  
  
## <a name="see-also"></a>参照  
 [scanf、_scanf_l、wscanf、_wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [書式指定フィールド: scanf 関数と wscanf 関数](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)   
 [scanf 関数の型フィールド文字](../c-runtime-library/scanf-type-field-characters.md)