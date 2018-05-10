---
title: 環境変数マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ebebb6e7d237746f96c7ac7e27c249244ff825b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="environment-variable-macros"></a>環境変数マクロ
(Nmake の) は、セッションの開始前に存在する環境変数のマクロ定義を継承します。 変数は、オペレーティング システムの環境で設定されている場合は、NMAKE マクロとして使用できます。 継承された名前は大文字に変換します。 継承は、前処理する前に発生します。 /E オプションを使用して、メイクファイルで同じ名前を持つすべてのマクロをオーバーライドする環境変数から継承されたマクロが発生します。  
  
 セッションで、環境変数マクロを再定義でき、これが、対応する環境変数を変更します。 SET コマンドで環境変数を変更することもできます。 SET コマンドを使用して、セッションで環境変数を変更するは変更されません、対応するマクロただし。  
  
 例えば:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 この例で、変更する`PATH`、対応する環境変数を変更`PATH`; の追加`\nonesuch`をパスにします。  
  
 環境変数がメイクファイルの正しい構文的になる文字列として定義されている場合は、マクロは作成されませんし、警告は生成されません。 変数の値にドル記号 ($) が含まれている場合 (nmake の) はそのマクロの呼び出しの先頭として解釈されます。 マクロを使用すると、予期しない動作が発生することができます。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)