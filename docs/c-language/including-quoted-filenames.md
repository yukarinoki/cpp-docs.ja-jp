---
title: 引用符で囲まれたファイル名を含む | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80f6afbc503b52d1ef620050bf5592eb84e75fa9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="including-quoted-filenames"></a>引用符で囲まれたファイル名を含む
**ANSI 3.8.2** インクルード可能なソース ファイルの引用された名前のサポート  
  
 2 組の二重引用符 (" ") 間にインクルード ファイルのあいまいでない完全なパスを指定すると、プリプロセッサはそのパスのみを検索し、標準ディレクトリを無視します。  
  
 [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" に指定されたインクルード ファイルでは、ディレクトリの検索は親ファイルのディレクトリから始まり、その後にすべての祖父母ファイルのディレクトリが検索されます。 したがって、検索は現在処理中のソース ファイルが含まれるディレクトリに対して相対的に開始されます。 親の親ファイルが存在せず、見つからなかった場合は、ファイル名が山かっこで囲まれているものとして検索が続行されます。  
  
## <a name="see-also"></a>参照  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)