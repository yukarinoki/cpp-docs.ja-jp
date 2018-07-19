---
title: system 関数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51c9e9e348f1cd1fbae9612c2d2ad1988af3b009
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386736"
---
# <a name="system-function"></a>system 関数
**ANSI 4.10.4.5** **system** 関数による文字列の実行の内容とモード  
  
 **system** 関数は、コマンド ラインからではなく、C プログラムから内部オペレーティング システム コマンド、.EXE、.COM (Windows NT の .CMD)、または .BAT ファイルを実行します。  
  
 system 関数は、コマンド インタープリターを探します。これは通常、Windows NT オペレーティング システムでは CMD.EXE、Windows では COMMAND.COM です。 system 関数は、続いてコマンド インタープリターに引数文字列を渡します。  
  
 詳細については、「[system、_wsystem](../c-runtime-library/reference/system-wsystem.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [ライブラリ関数](../c-language/library-functions.md)