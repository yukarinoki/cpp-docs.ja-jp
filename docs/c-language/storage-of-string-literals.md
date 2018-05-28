---
title: 文字列リテラルの格納 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d87998f7e9d579c012f5db2f38f20886c1e74c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="storage-of-string-literals"></a>文字列リテラルの格納
リテラル文字列の各文字は、連続するメモリ位置に順番に格納されます。 文字列リテラル内のエスケープ シーケンス (**\\\\** や **\\"** など) は、それぞれ 1 文字としてカウントされます。 (**\0** エスケープ シーケンスによって表される) null 文字は各文字列リテラルに自動的に追加され、その最後を示します (これは[変換フェーズ](../preprocessor/phases-of-translation.md) 7 で発生します)。2 つの同じ文字列が別々のアドレスに保存されない場合があることに注意してください。 [/GF](../build/reference/gf-eliminate-duplicate-strings.md) を指定すると、同じ文字列が複数ある場合に、その 1 つだけが実行可能ファイルに追加されます。  
  
## <a name="remarks"></a>コメント  
 **Microsoft 固有の仕様**  
  
 文字列には、静的ストレージ存続期間があります。 ストレージ存続期間については、「[ストレージ クラス](../c-language/c-storage-classes.md)」をご覧ください。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [C 文字列リテラル](../c-language/c-string-literals.md)