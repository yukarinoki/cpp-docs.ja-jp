---
title: ARM アセンブラー ディレクティブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5ab97fb9ccdff19206b829383c622efd3f7921
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053302"
---
# <a name="arm-assembler-directives"></a>ARM アセンブラー ディレクティブ
ほとんどの場合、Microsoft ARM アセンブラー言語を使用して、ARM アセンブリの第 7 章に記載されている、 [ARM アセンブラー ツール ガイド](http://go.microsoft.com/fwlink/p/?linkid=246102)です。 ただし、一部のアセンブリ ディレクティブの Microsoft 実装は、ARM assembly ディレクティブによって異なります。 この記事では、相違点について説明します。  
  
## <a name="microsoft-implementations-of-arm-assembly-directives"></a>Microsoft の ARM Assembly ディレクティブの実装  
 領域  
 Microsoft ARM アセンブラーは、これらの領域の属性をサポートしています: 揃えるには、コード、CODEALIGN、データ、NOINIT、読み取り専用、読み取り/書き込み、つまみ、ARM です。  
  
 親指と ARM 以外のすべての作業に記述されている、 [ARM アセンブラー ツール ガイド](http://go.microsoft.com/fwlink/p/?linkid=246102)です。  
  
 Microsoft ARM アセンブラーでは、THUMB は、コード セクションが Thumb コードが含まれ、コードのセクションでは既定値を示します。  ARM では、セクションが ARM コードが含まれていることを示します。  
  
 ATTR  
 サポートされていません。  
  
 コード 16  
 Microsoft ARM アセンブラーが許可されていない pre UAL Thumb 構文を使用すると、発生するので、サポートされていません。  代わりに、UAL 構文と共に THUMB ディレクティブを使用します。  
  
 一般的です  
 一般的な領域の配置の指定はサポートされていません。  
  
 DCDO  
 サポートされていません。  
  
 DN、QN、SN  
 型またはレジスタ エイリアスのレーンの仕様はサポートされていません。  
  
 エントリ  
 サポートされていません。  
  
 EQU  
 定義済みの記号の型の指定はサポートされていません。  
  
 エクスポートとグローバル  
 ```  
EXPORTsym {[type]}  
```  
  
 `sym` エクスポートする記号です。  `[type]`を指定する場合はいずれかであることができます`[DATA]`シンボルがデータをポイントすることを示すためにまたは`[FUNC]`シンボルがコードを指していることを示すためにします。  
  
 シノニムをエクスポートはグローバルです。  
  
 EXPORTAS  
 サポートされていません。  
  
 フレーム  
 サポートされていません。  
  
 関数とプロシージャ  
 Assembly 構文は、カスタムの仕様をサポートしていますは呼び出し元の保存と呼び出し先保存にあるもののレジスタを一覧表示して、プロシージャの呼び出し規約 Microsoft ARM アセンブラーは、構文を受け入れますが、登録リストは無視されます。  アセンブラーによって生成されるデバッグ情報には、既定の呼び出し規約のみがサポートしています。  
  
 インポートおよび EXTERN  
 ```  
IMPORT sym{, WEAK alias{, TYPE t}}  
```  
  
 `sym` インポートするシンボルの名前です。  
  
 弱い場合`alias`が指定されていることを示して`sym`弱い外部です。 リンク時に、その定義が見つからないかどうかは、すべての参照をバインド代わりに`alias`です。  
  
 場合型`t`が指定すると、`t`リンカーが解決を試行する方法を示す`sym`です。  これらの値`t`はことがあります。   
1-のライブラリの検索を実行できません `sym`  
2: ライブラリの検索を実行 `sym`  
3-`sym`のエイリアス`alias`(既定値)  
  
 EXTERN は点を除いて、インポートのシノニム`sym`への参照が現在のアセンブリ内にある場合にのみをインポートします。  
  
 MACRO  
 マクロの状態コードを保持する変数の使用はサポートされていません。 既定値マクロのパラメーターはサポートされていません。  
  
 NOFP  
 サポートされていません。  
  
 このことを選択すると、TTL、SUBT  
 Microsoft ARM アセンブラーで番組表が生成されないために、サポートされていません。  
  
 PRESERVE8  
 サポートされていません。  
  
 再配置します。  
 `RELOC n` 命令またはデータ定義ディレクティブに従うだけことができます。 シンボルがありません。"匿名"を再配置できることがあります。  
  
 必要があります。  
 サポートされていません。  
  
 REQUIRE8  
 サポートされていません。  
  
 THUMBX  
 Microsoft ARM アセンブラーが Thumb 2 ee 命令セットをサポートしていないためにサポートされていません。  
  
## <a name="see-also"></a>関連項目  
 [ARM アセンブラーのコマンド ライン リファレンス](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM アセンブラー診断メッセージ](../../assembler/arm/arm-assembler-diagnostic-messages.md)