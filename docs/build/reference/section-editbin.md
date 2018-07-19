---
title: -SECTION (EDITBIN) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e29e258b4fb661cfa06e057704bba983ad924f34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378354"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)
```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、セクションのオブジェクト ファイルがコンパイルまたはリンク時に設定された属性をオーバーライドするセクションの属性を変更します。  
  
 コロンの後に ( **:** )、指定、*名前*セクションのです。 次のセクションの名前を変更する*名前*は等号 (=) でと*newname*セクションのです。  
  
 設定または変更するセクションの`attributes`、コンマ区切り (**、**) 1 つまたは複数の属性の英文字で構成します。 属性を符号反転するには、感嘆符 (!) 付きの文字の前にします。 次の文字は、メモリの属性を指定します。  
  
|属性|設定|  
|---------------|-------------|  
|c|code|  
|d|破棄可能|  
|e|executable|  
|i|初期化されたデータ|  
|k|仮想メモリのキャッシュ|  
|m|リンクを削除します。|  
|o|リンク情報|  
|p|仮想メモリのページング|  
|r|読み取り|  
|s|shared|  
|u|初期化されていないデータ|  
|週|書き込み|  
  
 コントロールに*配置*、文字を指定**A**後に、次の文字を次のように、(バイト単位) の配置のサイズを設定する 1 つ。  
  
|文字|配置のサイズ (バイト単位)|  
|---------------|-----------------------------|  
|1|1|  
|2|2|  
|4|4|  
|9|8|  
|p|16|  
|t|32|  
|秒|64|  
|x|位置合わせなし|  
  
 指定、`attributes`と*配置*文字として空白を含む文字列。 文字では大文字小文字が区別されません。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)