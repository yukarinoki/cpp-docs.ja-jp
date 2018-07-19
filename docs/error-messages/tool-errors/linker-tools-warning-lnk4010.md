---
title: リンカー ツールの警告 LNK4010 |Microsoft ドキュメント
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
ms.openlocfilehash: 266e377a917fe3ce9ae7bae228134f49384e15cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302673"
---
# <a name="linker-tools-warning-lnk4010"></a>リンカー ツールの警告 LNK4010
無効なサブシステム バージョン番号番号です。既定のサブシステムのバージョンと見なされます  
  
 イメージのサブシステムのバージョンを指定することができます ([/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md))。 各サブシステムには、最小バージョン要件があります。 指定されたバージョンが、最小値よりも小さい場合は、この警告が発生し、リンカーが既定のサブシステムを使用するだけです。