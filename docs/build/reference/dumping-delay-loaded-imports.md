---
title: 遅延読み込みしたインポートのダンプ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29f2faecb29da93729b0be0f40c00c18b82f6344
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720877"
---
# <a name="dumping-delay-loaded-imports"></a>遅延読み込みしたインポートのダンプ

遅延読み込みしたインポートのダンプを使用して[dumpbin/imports](../../build/reference/imports-dumpbin.md)標準インポートよりも若干異なる情報を表示します。 ダンプ/imports の独自のセクションに分離され、遅延読み込みしたインポート明示的に付いています。 イメージに含まれている情報をアンロードする場合は、それが表示されます。 バインド情報がある場合、インポートのバインド アドレスと DLL のターゲットの日付/時刻スタンプが表示されます。

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)