---
title: '翻訳: 診断 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d297cfd4f4dee49d3344ae2f159f85682f05ea2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017587"
---
# <a name="translation-diagnostics"></a>変換: 診断

**ANSI 2.1.1.3** 診断を識別する方法

Microsoft C は、次の形式のエラー メッセージを生成します。

> *filename* **(** *line-number* **) :** *diagnostic* **C**<em>number</em> *message*

ここで、*filename* はエラーが発生したソース ファイルの名前、*line-number* はコンパイラがエラーを検出した行番号、*diagnostic* は "error" または "warning"、*number* は (構文に示すように先頭に **C** が付いた) 一意の 4 桁の番号、*message* は説明メッセージです。

## <a name="see-also"></a>参照

[実装で定義された動作](../c-language/implementation-defined-behavior.md)