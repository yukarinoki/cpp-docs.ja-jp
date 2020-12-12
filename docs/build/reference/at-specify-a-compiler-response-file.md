---
description: '詳細情報: @ (コンパイラ応答ファイルの指定)'
title: '@ (コンパイラ応答ファイルの指定)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: bd2859f7973723d93594693902e92ac3530d73ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182893"
---
# <a name="-specify-a-compiler-response-file"></a>@ (コンパイラ応答ファイルの指定)

コンパイラ応答ファイルを指定します。

## <a name="syntax"></a>構文

> **\@**<em>response_file</em>

## <a name="arguments"></a>引数

*response_file*<br/>
コンパイラコマンドを含むテキストファイル。

## <a name="remarks"></a>解説

応答ファイルには、コマンドラインで指定する任意のコマンドを含めることができます。 これは、コマンドライン引数が127文字を超えている場合に便利です。

応答ファイル内からオプションを指定することはできません **\@** 。 つまり、応答ファイルは別の応答ファイルを埋め込むことができません。

コマンドラインから、任意の数の応答ファイルオプション (たとえば、) を指定でき `@respfile.1 @respfile.2` ます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

- 応答ファイルは、開発環境内から指定することはできません。また、コマンドラインで指定する必要があります。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラオプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
