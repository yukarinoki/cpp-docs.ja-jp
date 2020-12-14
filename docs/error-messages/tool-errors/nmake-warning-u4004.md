---
description: 詳細については、「NMAKE Warning U4004」を参照してください。
title: NMAKE の警告 U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: 44326bfb6a69b583967163054b4510bf5c50d6bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345291"
---
# <a name="nmake-warning-u4004"></a>NMAKE の警告 U4004

ターゲット ' targetname ' に対するルールが多すぎます

1つのコロン (**:**) を区切り記号として使用して、指定されたターゲットに複数の説明ブロックが指定されました。 NMAKE は、最初の説明ブロックのコマンドを実行し、後のブロックは無視します。

複数の依存関係で同じターゲットを指定するには、 `::` 各依存関係行の区切り記号として2つのコロン () を使用します。
