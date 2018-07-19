---
title: -仮想ディスク (ディスプレイスメントの無効化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vd
dev_langs:
- C++
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6a7b9bacc95c668c1c0f59a3dba172d58c607d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377598"
---
# <a name="vd-disable-construction-displacements"></a>/vd (ディスプレイスメントの無効化)
## <a name="syntax"></a>構文  
  
```  
/vdn  
```  
  
## <a name="arguments"></a>引数  
 `0`  
 Vtordisp コンストラクター/デストラクター ディスプレイスメント メンバーを抑制します。 すべてのクラスのコンス トラクターとデストラクターを呼び出す仮想ことがわかっている場合にのみ、このオプションが事実上機能を選択します。  
  
 `1`  
 隠し vtordisp コンストラクター/デストラクター ディスプレイスメント メンバーの作成を有効にします。 このオプションは、既定値です。  
  
 `2`  
 使用できるように[dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)構築されるオブジェクト。 たとえば、仮想基底クラスから派生クラスへの dynamic_cast です。  
  
 **/vd2**仮想関数を使用して仮想ベースがある場合は、vtordisp フィールドを追加します。 **/vd1**すれば十分です。 最も一般的なケース **/vd2**が必要なは、仮想ベース内の唯一の仮想関数がデストラクターです。  
  
## <a name="remarks"></a>コメント  
 これらのオプションは、仮想基底を使用する C++ コードにのみ適用されます。  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 仮想継承が使用されている状況で C++ ディスプレイスメントをサポートを実装します。 ディスプレイスメントは仮想関数の場合、仮想ベースで宣言され、派生クラスでオーバーライドされるときに作成の問題を解決、さらに派生クラスの構築中にコンス トラクターから呼び出されます。  
  
 問題が仮想関数が渡されるが正しくない`this`ポインターその結果、仮想変位間の不一致の基底クラスとその派生クラスにします。 ソリューションでは、各仮想基本クラスの vtordisp フィールドと呼ばれる 1 つ構築変位の調整を提供します。  
  
 既定では、コードがユーザー定義のコンス トラクターとデストラクターを定義し、仮想ベースの仮想関数がオーバーライドされるたびに、vtordisp フィールドが導入されました。  
  
 これらのオプションでは、ソース ファイル全体に影響します。 使用して[vtordisp](../../preprocessor/vtordisp.md)を抑制し、クラス単位で vtordisp フィールドを再度有効にします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)