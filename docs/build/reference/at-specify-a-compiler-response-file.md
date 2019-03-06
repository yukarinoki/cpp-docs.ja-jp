---
title: '@ (コンパイラ応答ファイルの指定)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: dc61477da9547204acfce93bbedcd077787162c2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416957"
---
# <a name="-specify-a-compiler-response-file"></a>@ (コンパイラ応答ファイルの指定)

コンパイラ応答ファイルを指定します。

## <a name="syntax"></a>構文

> **\@**<em>response_file</em>

## <a name="arguments"></a>引数

*response_file*<br/>
コンパイラのコマンドを含むテキスト ファイル。

## <a name="remarks"></a>Remarks

応答ファイルは、コマンドラインで指定する任意のコマンドを含めることができます。 コマンドライン引数は、127 文字を超えた場合に便利なことができます。

指定することはできません、 **\@** から応答ファイル内のオプションします。 つまり、応答ファイルには、別の応答ファイルを埋め込むことはできません。

コマンドラインから多くの応答ファイル オプションを指定できます (たとえば、 `@respfile.1 @respfile.2`) します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

- 応答ファイルは、開発環境内から指定することはできませんし、コマンドラインで指定する必要があります。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
