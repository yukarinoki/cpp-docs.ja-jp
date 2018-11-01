---
title: リンカー ツールの警告 LNK4010
ms.date: 11/04/2016
f1_keywords:
- LNK4010
helpviewer_keywords:
- LNK4010
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
ms.openlocfilehash: 3f25c9194f48df4064282fb8601928b3ff00f40e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558796"
---
# <a name="linker-tools-warning-lnk4010"></a>リンカー ツールの警告 LNK4010

無効なサブシステム バージョン番号番号です。既定サブシステムのバージョンと見なされます

イメージのサブシステムのバージョンを指定することができます ([/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md))。 各サブシステムでは、最小バージョン要件があります。 指定されたバージョンが、最小値よりも小さい場合は、この警告が発生し、リンカーが既定のサブシステムを使用するだけです。