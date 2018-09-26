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
ms.openlocfilehash: 70a31d32ce7bdf89cd0216926c6628b4fa7bdd27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027352"
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
