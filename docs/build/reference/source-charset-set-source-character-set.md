---
title: -ソース-文字セット (ソース文字セット) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- source-charset
- /source-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 722586f3a629535c5ea70c26e5172e6bc7ecb418
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213081"
---
# <a name="source-charset-set-source-character-set"></a>/source-charset (ソース文字セット)
ソース文字セットの実行可能ファイルを指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
/source-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>引数  
 **IANA_name**  
 IANA で定義されている文字セットの名前。  
  
 **CPID**  
 10 進数としてコード ページ id。  
  
## <a name="remarks"></a>Remarks  
 使用することができます、 **/source-charset**ソース ファイルが、基本ソース文字セットには表されない文字を含めるときに使用する、拡張ソース文字セットを指定するオプション。 ソース文字セットは、コンパイル前に、プリプロセス フェーズへの入力として使用される内部表現に、プログラムのソース テキストを解釈するために使用するエンコードします。 内部表現は、実行可能ファイルに文字列および文字の値を格納する、実行文字セットに変換されます。 IANA のいずれかを使用する ISO 文字セットの名前、またはドット (.) の後に使用する文字セットを指定する 3 ~ 5 桁の 10 進コード ページ識別子。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](/windows/desktop/Intl/code-page-identifiers)します。  
  
 既定では、Visual Studio は、utf-8 または utf-16、たとえば、ソース ファイルが、エンコードされた Unicode 形式であるか判断のバイト順マークを検出します。 バイト順マークが見つからない場合は、ソース ファイルを使ってエンコードされるユーザーの現在のコード ページで、文字を使用して名前またはコード ページの設定を指定しない限り、想定しています。、 **/source-charset**オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存できます。 ソースと実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語ドキュメント。  
  
 指定するソース文字セットは、文字セット内の同じコード ポイントを 7 ビット ASCII 文字をマップする必要があります。 または多くのコンパイル エラーが次の可能性があります。 ソース文字セットも utf-8 によって encodable 設定拡張の Unicode 文字にマップ可能な場合があります。 Encodable を utf-8 ではない文字は、実装に固有の代替で表されます。 Microsoft コンパイラでは、これらの文字を疑問符 () を使用します。  
  
 使用することができます、ソース文字セットと、実行文字セットの両方を utf-8 に設定する場合、 **/utf-8**ショートカットとしてコンパイラ オプション。 指定することと同じである **/source -charset:utf-8/execution-charset:utf-8**コマンド行にします。 これらのいずれかのオプションも有効、 **/validate-charset**既定ではオプションです。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  展開、**構成プロパティ**、 **C/C++**、**コマンドライン**フォルダー。  
  
3.  **オプションの高度な**、追加、 **/source-charset**オプション、および、使用するエンコーディングを指定します。  
  
4.  **OK** を選択して変更を保存してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (実行文字セット)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (互換性のある文字の検証)](../../build/reference/validate-charset-validate-for-compatible-characters.md)