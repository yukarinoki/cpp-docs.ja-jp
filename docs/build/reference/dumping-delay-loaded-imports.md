---
description: '詳細情報: 遅延読み込みされたインポートのダンプ'
title: 遅延読み込みされたインポートのダンプ
ms.date: 01/19/2021
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.openlocfilehash: 6a0fec0b10bc29ea919195302334a25f71de0abd
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666915"
---
# <a name="dump-delay-loaded-imports"></a>遅延読み込みされたインポートのダンプ

遅延読み込みされたインポートは、を使用してダンプでき [`dumpbin /imports`](imports-dumpbin.md) ます。 これらのインポートは、標準のインポートとは少し異なる情報で表示されます。 これらは、リストの独自のセクションに分離 `/imports` され、遅延読み込みのインポートとして明示的にラベル付けされます。 イメージにアンロード情報が含まれている場合は、そのことに注意してください。 バインド情報が存在する場合は、インポートのバインドされたアドレスと共に、ターゲット DLL の時刻と日付のスタンプが示されます。

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
