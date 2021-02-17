---
description: 詳細については、「コンパイラエラー C2855」を参照してください。
title: コンパイラ エラー C2855
ms.date: 02/16/2021
f1_keywords:
- C2855
helpviewer_keywords:
- C2855
ms.openlocfilehash: cc26dbf92ea385ee05681e5fab8b5c4257c2b525
ms.sourcegitcommit: e99db7c3b5f25ece0e152165066c926751a7c2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "100643548"
---
# <a name="compiler-error-c2855"></a>コンパイラ エラー C2855

> コマンドラインオプション '*option*' がプリコンパイル済みヘッダーと一致しません

このエラーは、コマンドラインオプションがプリコンパイル済みヘッダーの作成に使用されるオプションと異なる場合に発生します。

## <a name="remarks"></a>解説

エラー C2855 は、コンパイラオプションを変更した後にインクリメンタルビルドを行うときに発生する可能性があります。 また、個々のソースファイルに対して特定のコンパイラオプションを設定した場合にも発生する可能性があります。

このエラーを解決するには、指定されたコマンドラインオプションを使用して、プリコンパイル済みヘッダーを再生成します。 プリコンパイル済みヘッダーを再生成するには、関連付けられているソースファイルをビルドします。 たとえば、Visual Studio テンプレートによって作成されたプロジェクトでは、通常、 *`pch.cpp`* プリコンパイル済みヘッダーを生成するためのという名前のソースファイルが作成されます。 (以前のバージョンの Visual Studio では、このファイルにはという名前が付けられて *`stdafx.cpp`* います)。他のプロジェクトでは、リビルドするソースファイルは、 [ `/Yc` (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)コンパイラオプションを使用してビルドされたものです。 プリコンパイル済みヘッダーを変更した後、プロジェクト全体をリビルドすることをお勧めします。

## <a name="see-also"></a>関連項目

[`/Y` (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)\
[プリコンパイル済みヘッダー ファイル](../../build/creating-precompiled-header-files.md)
