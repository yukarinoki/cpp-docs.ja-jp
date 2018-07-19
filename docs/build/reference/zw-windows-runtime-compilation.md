---
title: -ZW (Windows ランタイムのコンパイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs:
- C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fce6c6825ed4ae715a2f4cde6b0e1ffa8b3b6733
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380067"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows ランタイムのコンパイル)
ソース コードをサポートするためにコンパイル[!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) のユニバーサル Windows プラットフォーム (UWP) アプリを作成するためです。  
  
 使用すると **/ZW**をコンパイルするには、常に指定 **/EHsc**もします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
/ZW /EHsc  
/ZW:nostdlib /EHsc  
```  
  
## <a name="arguments"></a>引数  
 nostdlib  
 Platform.winmd、Windows.Foundation.winmd、および他の既定の Windows メタデータ (.winmd) ファイルがコンパイルで自動に含まれていないことを示します。 代わりに、使用する必要があります、 [/FU (Name Forced #using ファイルの using)](../../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプションを Windows メタデータ ファイルを明示的に指定します。  
  
## <a name="remarks"></a>コメント  
 指定すると、 **/ZW**オプション、コンパイラは、これらの機能をサポートしています。  
  
-   必要なメタデータ ファイル、名前空間、データ型、および Windows ランタイムで実行するアプリを必要とする関数。  
  
-   Windows ランタイム オブジェクトの参照カウントおよび自動参照カウントがゼロになるオブジェクトの破棄を自動化します。  
  
 インクリメンタル リンカーを使用して .obj ファイルに含まれる Windows メタデータをサポートしていないため、 **/ZW**オプション、 [/Gm (簡易リビルドの有効)](../../build/reference/gm-enable-minimal-rebuild.md)オプションと互換性がありません **/ZW**.  
  
 詳細については、次を参照してください。 [Visual c 言語リファレンス](../../cppcx/visual-c-language-reference-c-cx.md)です。  
  
## <a name="requirements"></a>要件  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)