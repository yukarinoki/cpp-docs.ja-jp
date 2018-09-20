---
title: 2.8 ディレクティブのバインディング |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc5b702b17e01bb8d4625a837abdb71086113e68
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415903"
---
# <a name="28-directive-binding"></a>2.8 ディレクティブのバインディング

ディレクティブの動的バインドは、次の規則に従う必要があります。

- **の**、**セクション**、**単一**、**マスター**、および**バリア**ディレクティブのバインドを動的にそれを囲む**並列**いずれかの値に関係なく、存在する場合、**場合**そのディレクティブに存在する可能性のある句。 並列領域が現在実行されていない、ディレクティブは、マスター スレッドのみから成るチームによって実行されます。

- **注文**ディレクティブに動的にそれを囲むバインド**の**します。

- **アトミック**ディレクティブを排他アクセスを強制する**アトミック**現在のチームだけでなく、すべてのスレッドでのディレクティブ。

- **重要な**ディレクティブを排他アクセスを強制する**重要な**現在のチームだけでなく、すべてのスレッドでのディレクティブ。

- ディレクティブとも、最も近い外側の任意のディレクティブを動的にバインドできませんを囲む**並列**します。