---
title: コマンド マクロおよびオプション マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab8b1d61c2c4f6ae9125b8eefaf05f791f57b259
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367360"
---
# <a name="command-macros-and-options-macros"></a>コマンド マクロとオプション マクロ
コマンド マクロは Microsoft 製品の定義済みです。 オプション マクロは、これらの製品にオプションを表し、既定では未定義です。 両方定義済みの推論規則で使用され、記述ブロックまたはユーザー定義の推論規則で使用できます。 コマンド マクロは、オプションを含むコマンドラインの一部またはすべてを表す再定義することができます。 オプション マクロは、左の未定義の場合、null 文字列を生成します。  
  
|Microsoft の製品|コマンド マクロ|として定義されています。|オプション マクロ|  
|-----------------------|-------------------|----------------|-------------------|  
|マクロ アセンブラー|**AS**|ml|**AFLAGS**|  
|基本的なコンパイラ|**ビジネス継続性**|ビジネス継続性|**BFLAGS**|  
|C コンパイラ|**[CC]**|cl|**CFLAGS**|  
|C++ コンパイラ|**CPP**|cl|**CPPFLAGS**|  
|C++ コンパイラ|**CXX であります。**|cl|**ように**|  
|Resource Compiler|**RC**|rc|**RFLAGS**|  
  
## <a name="see-also"></a>関連項目  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)