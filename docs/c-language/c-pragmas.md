---
title: C プラグマ | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pragmas, C/C++
ms.assetid: 3d6d36b4-d565-4632-a4cd-e39aeaded5ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a87a6518eec495961d1f8d40c625e589db01bd3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382115"
---
# <a name="c-pragmas"></a>C プラグマ

**Microsoft 固有の仕様**

"*プラグマ*" は、コンパイル時に特定のアクションを実行するようにコンパイラに指示します。 プラグマは、コンパイラごとに異なります。 たとえば、**optimize** プラグマを使用すると、プログラムで実行する最適化を設定できます。 Microsoft C のプラグマは、次のとおりです。

|||||
|-|-|-|-|
|**alloc_text**|**data_seg**|**inline_recursion**|**setlocale**|
|**auto_inline**|**function**|**intrinsic**|**warning**|
|**check_stack**|**hdrstop**|**message**||
|**code_seg**|**include_alias**|**optimize**||
|**comment**|**inline_depth**|**pack**||

Microsoft C コンパイラのプラグマについては、「[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)」をご覧ください。

 **Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)  
