---
description: 詳細については、「リソースコンパイラの警告 RC4093」を参照してください。
title: リソース コンパイラの警告 RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 40f4777bb62fc2a5e434a4a365cdd027a04ffafd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237089"
---
# <a name="resource-compiler-warning-rc4093"></a>リソース コンパイラの警告 RC4093

アクティブでないコード内の文字定数でエスケープ解除される改行

`#if`、 `#elif` 、 **#Ifdef**、または **#ifndef** プリプロセッサディレクティブの定数式が0に評価され、コードが非アクティブになります。 この非アクティブコード内では、改行文字が単一引用符または二重引用符のセット内に表示されます。

次の二重引用符までのすべてのテキストは、文字定数内にあると見なされます。
