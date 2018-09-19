---
title: インポート ライブラリとエクスポート ファイルの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28b4b94025c813ea526964ed6395a2e6af1ac0b9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721241"
---
# <a name="working-with-import-libraries-and-export-files"></a>インポート ライブラリとエクスポート ファイル

/DEF オプションを使用して LIB を使用すると、インポート ライブラリとエクスポート ファイルを作成します。 リンクの使用を含むプログラムをビルドするファイルのエクスポートは、(通常は、ダイナミック リンク ライブラリ (DLL)) をエクスポートし、他のプログラムでこれらのエクスポートへの参照を解決するのには、インポート ライブラリを使用します。

.Dll を作成する前に、準備手順で、インポート ライブラリを作成する場合を渡す必要がある同じ一連のオブジェクト ファイル、.dll を作成するときにインポート ライブラリを構築するときに渡されたことに注意してください。

ほとんどの場合は LIB を使用して、インポート ライブラリを作成する必要はありません。 エクスポートを含むプログラム (実行可能ファイルまたは DLL) をリンクする場合のリンクは自動的にエクスポートを記述するインポート ライブラリを作成します。 その後、これらのエクスポートを参照しているプログラムをリンクする場合は、インポート ライブラリを指定します。

ただし、DLL のエクスポートからもインポートするプログラムをかどうか直接的または間接的にする必要がありますを使用して、LIB インポート ライブラリのいずれかを作成します。 LIB、インポート ライブラリを作成する場合も、エクスポート ファイルを作成します。 Dll のいずれかをリンクするときに、エクスポート ファイルを使用する必要があります。

## <a name="see-also"></a>関連項目

[LIB リファレンス](../../build/reference/lib-reference.md)