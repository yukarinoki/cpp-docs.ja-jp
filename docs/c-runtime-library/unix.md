---
title: UNIX
description: プログラムを Unix に移植するためのガイドライン。
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- unix
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
ms.openlocfilehash: 07f5ffeec8696ded5880c45ed2ea1a5107bee48c
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590148"
---
# <a name="unix"></a>UNIX

プログラムを UNIX に移植する場合は、次のガイドラインに従ってください。

- SYS サブディレクトリからはヘッダーファイルを削除しないでください。 SYS ヘッダーファイルは、プログラムを UNIX に転送する予定がない場合にのみ、他の場所に配置できます。

- 引数としてパスとファイル名を表す文字列を実行するルーチンでは、UNIX と互換性のあるパス区切り記号を使用します。 UNIX では、この目的のためにスラッシュ (/) のみをサポートしていますが、Win32 オペレーティングシステムでは、円記号 () とスラッシュ (/) の両方がサポートされてい \\ ます。 このドキュメントでは、などのステートメントで、UNIX と互換性のあるスラッシュをパス区切り記号として使用し `#include` ます。 (ただし、Windows オペレーティングシステムのコマンドシェルである CMD.EXE は、コマンドプロンプトで入力されたコマンドのスラッシュをサポートしていません)。

- UNIX で正しく動作するパスとファイル名を使用します。これは大文字と小文字が区別されます。 Win32 オペレーティングシステムのファイルアロケーションテーブル (FAT) ファイルシステムでは、大文字と小文字が区別されません。 NTFS ファイルシステムでは、ディレクトリの一覧の大文字と小文字が維持されますが、ファイルの検索やその他のシステム操作は無視されます。

> [!NOTE]
>  このバージョンの Visual C++ では、UNIX と互換性のある情報は、関数の説明から削除されています。

## <a name="see-also"></a>関連項目

[互換性](../c-runtime-library/compatibility.md)
