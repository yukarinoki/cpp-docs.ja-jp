---
title: 文字シーケンス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85cf817a4d50346b9d10a9a9d1bc27abb5904433
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382391"
---
# <a name="character-sequences"></a>文字シーケンス
**ANSI 3.8.2** ソース ファイルの文字シーケンスのマッピング  
  
 プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。  
  
 したがって、インクルード ファイルのパスを指定するには、1 つの円記号 (バックスラッシュ) のみを使用します。  
  
```  
#include "path1\path2\myfile"  
```  
  
 ソース コード内では、次のように、2 つの円記号 (バックスラッシュ) が必要です。  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>参照  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)