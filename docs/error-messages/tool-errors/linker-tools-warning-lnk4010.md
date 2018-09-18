---
title: リンカー ツールの警告 LNK4010 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4010
dev_langs:
- C++
helpviewer_keywords:
- LNK4010
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e214f603c31c72533d81a140023363880532191c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068072"
---
# <a name="linker-tools-warning-lnk4010"></a>リンカー ツールの警告 LNK4010

無効なサブシステム バージョン番号番号です。既定サブシステムのバージョンと見なされます

イメージのサブシステムのバージョンを指定することができます ([/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md))。 各サブシステムでは、最小バージョン要件があります。 指定されたバージョンが、最小値よりも小さい場合は、この警告が発生し、リンカーが既定のサブシステムを使用するだけです。