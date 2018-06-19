---
title: インポート ライブラリとエクスポート ファイルの操作 |Microsoft ドキュメント
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
ms.openlocfilehash: bc2e5b6b1f2a459d7a00e48ff1aaafff38803871
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377933"
---
# <a name="working-with-import-libraries-and-export-files"></a>インポート ライブラリとエクスポート ファイル
/DEF オプションを使用して LIB を使用して、インポート ライブラリとエクスポート ファイルを作成することができます。 リンクの使用を含むプログラムをビルドするファイルのエクスポートが (通常、ダイナミック リンク ライブラリ (DLL)) をエクスポートし、他のプログラムでこれらのエクスポートへの参照を解決するのには、インポート ライブラリを使用します。  
  
 .Dll を作成する前に、準備手順で、インポート ライブラリを作成する場合を渡す必要がある同じ一連のオブジェクト ファイル、.dll を構築するときにインポート ライブラリを構築するときに渡したものとに注意してください。  
  
 ほとんどの状況では LIB を使用して、インポート ライブラリを作成する必要はありません。 エクスポートを含むプログラム (実行可能ファイルまたは DLL) をリンクするときのリンクは自動的にエクスポートを記述したインポート ライブラリを作成します。 後で、これらのエクスポートを参照しているプログラムをリンクする場合は、インポート ライブラリを指定します。  
  
 ただし、DLL のエクスポートからもインポートするプログラムをかどうか直接的または間接的に行う必要があります LIB インポート ライブラリのいずれかを作成します。 LIB は、インポート ライブラリを作成するときも、エクスポート ファイルを作成します。 Dll のいずれかをリンクするときに、エクスポート ファイルを使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [LIB リファレンス](../../build/reference/lib-reference.md)