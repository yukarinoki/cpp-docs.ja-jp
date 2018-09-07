---
title: ファイル名マクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc231dfb156460a2a0cc383b6d038a98c6e2015b
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894409"
---
# <a name="filename-macros"></a>ファイル名マクロ

依存関係 (ディスク上のファイル名を完全にではなく仕様) で指定されたファイル名には、ファイル名マクロが定義済みです。 これらのマクロを呼び出すときにかっこで囲む必要はありません。よう $ のみを指定します。

|マクロ|説明|
|-----------|-------------|
|**$\@**|現在のターゲットの完全名 (パス、基本の名前、拡張機能) は、現在指定されています。|
|**$$\@**|現在のターゲットの完全名 (パス、基本の名前、拡張機能) は、現在指定されています。 依存関係で依存関係としてのみ有効です。|
|**$&#42;**|ファイル拡張子を取り除いた現在のターゲットのパスと基本名。|
|**$&#42;&#42;**|現在のターゲットのすべての依存します。|
|**$?**|現在のターゲットより後のタイムスタンプを持つすべての依存します。|
|**$<**|現在のターゲットより後のタイムスタンプを持つ依存ファイル。 推論規則のコマンドでのみ有効です。|

定義済みのファイル名マクロの一部を指定するには、マクロの修飾子を追加し、変更後のマクロをかっこで囲みます。

|修飾子|ファイル名の部分|
|--------------|-----------------------------|
|**D**|ドライブとディレクトリ|
|**B**|ベース名|
|**F**|ベース名と拡張子|
|**R**|ドライブ、ディレクトリ、およびベース名|

## <a name="see-also"></a>関連項目

[NMAKE の特殊マクロ](../build/special-nmake-macros.md)
