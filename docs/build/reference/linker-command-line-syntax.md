---
title: リンカー コマンドラインの構文 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd5b1b809bfbbb01bca91f3677774d396515f56e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376167"
---
# <a name="linker-command-line-syntax"></a>リンカー コマンド ラインの構文
リンクを実行します。実行可能ファイルを次のコマンド構文を使用します。  
  
```  
LINK arguments  
```  
  
 `arguments`オプションとファイル名を含めるし、任意の順序で指定することができます。 オプションは、処理された最初に、次のファイルです。 引数を区切るには、1 つ以上のスペースまたはタブを使用します。  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 コマンド ライン オプションはで構成されますオプション指定子では、ダッシュ (-) またはスラッシュ (/) の後に、オプションの名前。 オプション名の省略形は使用できません。 いくつかのオプションは、コロン (:) の後ろに指定された引数を取る。 スペースまたはタブを除きは許可されません、オプションの指定に/COMMENT オプションの引用符で囲まれた文字列内で。 10 進数または C 言語表記で数値の引数を指定します。 オプション名、およびその引数としてキーワードやファイル名は大文字と小文字が区別されませんが、引数としての識別子は大文字小文字を区別します。  
  
 ファイルをリンカーに渡すするには、リンク コマンドの後に、コマンドラインでファイル名を指定します。 ファイル名は、絶対または相対パスを指定して、ファイル名にワイルドカードを使用することができます。 ドット (.) とファイル名拡張子を省略すると、リンク ファイルの .obj と見なされます。 リンクや使用しないファイル名拡張子がないことにファイルの内容に関する想定をする確認するには、ファイルの種類を決定し、適宜処理します。  
  
 link.exe は、成功 (エラーなし)、0 を返します。  それ以外の場合、リンカーは、リンクを停止したエラー数を返します。  たとえば、リンカーは、LNK1104 を生成する場合、リンカーは 1104 を返します。  同様に、エラーが発生した、リンカーによって返される最小のエラー番号は、1000 です。  128 の戻り値は、オペレーティング システムまたは .config ファイルのいずれかの構成に問題を表しますlink.exe か c2.dll、ローダーが読み込まれませんでした。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)