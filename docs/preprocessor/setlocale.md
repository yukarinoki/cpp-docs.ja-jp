---
title: setlocale、_wsetlocale |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cfabfa3c83fe2ff90a6f7dbe07d5205f7a6f9a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="setlocale"></a>setlocale
ワイド文字定数、リテラル文字列を変換するときに使用するロケール (国/地域および言語) を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>コメント  
 マルチバイト文字をワイド文字に変換するアルゴリズムはロケールやコンパイルによって異なる場合や、実行可能ファイルを実行するロケールとは別のロケールでコンパイルされる場合があるため、このプラグマはコンパイル時にターゲットのロケールを指定する方法を提供します。 これによって、ワイド文字列が必ず正しい形式で保存されるようになります。  
  
 既定値*ロケール文字列*は""です。  
  
 "C" ロケールは、文字列の各文字を `wchar_t` (unsigned short) として値にマップします。 その他の値として有効な`setlocale`内にあるエントリです、[言語識別文字列](../c-runtime-library/language-strings.md) ボックスの一覧です。 たとえば、次のように発行します。  
  
```  
#pragma setlocale("dutch")  
```  
  
 言語文字列を発行する機能は、コンピューター上でのコード ページおよび言語 ID のサポートによって異なります。  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)