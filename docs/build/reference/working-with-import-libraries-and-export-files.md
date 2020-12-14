---
description: 詳細については、インポートライブラリの操作とファイルのエクスポートに関するページを参照してください。
title: インポート ライブラリとエクスポート ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: b6e1664aedf5fa87d269e0ff250e6c52d9d18259
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258799"
---
# <a name="working-with-import-libraries-and-export-files"></a>インポート ライブラリとエクスポート ファイル

/DEF オプションと共に LIB を使用して、インポートライブラリとエクスポートファイルを作成できます。 LINK はエクスポートファイルを使用して、エクスポートを含むプログラム (通常はダイナミックリンクライブラリ (DLL)) をビルドします。また、インポートライブラリを使用して、他のプログラムのエクスポートへの参照を解決します。

準備手順でインポートライブラリを作成する場合は、.dll を作成する前に、.dll をビルドするときに、インポートライブラリのビルド時に渡されたものと同じオブジェクトファイルのセットを渡す必要があることに注意してください。

ほとんどの場合、LIB を使用してインポートライブラリを作成する必要はありません。 エクスポートを含むプログラム (実行可能ファイルまたは DLL) をリンクすると、そのエクスポートを説明するインポートライブラリがリンクによって自動的に作成されます。 後で、これらのエクスポートを参照するプログラムをリンクするときに、インポートライブラリを指定します。

ただし、DLL を直接または間接的にインポート元のプログラムにエクスポートする場合は、LIB を使用していずれかのインポートライブラリを作成する必要があります。 LIB によってインポートライブラリが作成されると、エクスポートファイルも作成されます。 Dll のいずれかをリンクするときは、エクスポートファイルを使用する必要があります。

## <a name="see-also"></a>関連項目

[LIB リファレンス](lib-reference.md)
