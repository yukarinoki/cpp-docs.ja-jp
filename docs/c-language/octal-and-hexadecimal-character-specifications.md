---
title: 8 進文字と 16 進文字の仕様 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- octal characters
- hexadecimal characters
ms.assetid: 9264f3ec-46b8-41a5-b21a-8f7ed0a11871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f5709ef6fdcaaceecc79cd635374ee77d537100
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387389"
---
# <a name="octal-and-hexadecimal-character-specifications"></a>8 進文字と 16 進文字の仕様
シーケンス **\\***ooo* は、3 桁の 8 進数コードで ASCII 文字セットの任意の文字を指定できることを意味します。 8 進数の数値は、目的の文字またはワイド文字の値を指定します。  
  
 同様に、シーケンス **\x***hhh* を使用すると、ASCII 文字を 16 進文字コードとして指定できます。 たとえば、通常の C エスケープ シーケンス (**\b**) として ASCII バックスペース文字を指定するか、**\010** (8 進数) または **\x008** (16 進数) としてその文字をコード化できます。  
  
 8 進数のエスケープ シーケンスで使用できるのは、0 ～ 7 の数値のみです。 8 進数のエスケープ シーケンスは、3 桁を超えることはなく、8 進数値ではない最初の文字で終了します。 3 桁の数字をすべて使用する必要はありませんが、少なくとも 1 つを使用する必要があります。 たとえば、8 進数表現では、**\10** は ASCII フォールバック文字を表し、**\101** は文字 A を表します (ASCII チャートを参照)。  
  
 同様に、16 進数のエスケープ シーケンスには 1 桁以上を使用する必要がありますが、2 桁目と 3 桁目は省略できます。 したがって、**\x8**、**\x08**、または **\x008** として、バックスペース文字に 16 進数のエスケープ シーケンスを指定できます。  
  
 8 進数または 16 進数のエスケープ シーケンスの値は、文字定数の型 **unsigned char** およびワイド文字定数の型 `wchar_t` の表現可能な値の範囲内である必要があります。 ワイド文字定数については、「[マルチバイト文字とワイド文字](../c-language/multibyte-and-wide-characters.md)」を参照してください。  
  
 8 進数のエスケープ定数とは異なり、エスケープ シーケンスでの 16 進数の桁数に制限はありません。 16 進数のエスケープ シーケンスは、16 進数ではない数字では最初の文字で終了します。 16 進数の数字には **a** から **f** の文字が含まれるため、エスケープ シーケンスが目的の数字で終わることを確認する注意が必要です。 混乱を回避するには、マクロ定義に 8 進形式または 16 進形式の文字定義を配置できます:  
  
```  
#define Bell '\x07'  
```  
  
 16 進数の場合、正しい値を明確に示すように文字列を分割できます。  
  
```  
"\xabc"    /* one character  */  
"\xab" "c" /* two characters */  
```  
  
## <a name="see-also"></a>参照  
 [C 文字定数](../c-language/c-character-constants.md)