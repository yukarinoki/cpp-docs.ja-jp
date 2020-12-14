---
description: '詳細情報: 致命的なエラー C1902'
title: 致命的なエラー C1902
ms.date: 11/04/2016
f1_keywords:
- C1902
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
ms.openlocfilehash: e41f1d6fa9e15f9ed748b6e916ef8d8dd314b3f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276089"
---
# <a name="fatal-error-c1902"></a>致命的なエラー C1902

プログラムデータベースマネージャーが一致しません。インストールを確認してください

プログラムデータベースファイル (.pdb) は、システムで検出されたものより新しいバージョンの mspdb *XXX*.dll を使用して作成されました。 このエラーは通常、mspdbsrv.exe または mspdbcore.dll が不足しているか、または mspdb *XXX*.dll とは異なるバージョンを持っていることを示します。 (Mspdb *xxx*.dll ファイル名の *xxx* プレースホルダーは、各製品リリースで変更されます。 たとえば、Visual Studio 2015 では、ファイル名は mspdb140.dll です)。

mspdbsrv.exe、mspdbcore.dll、および mspdb *XXX*.dll の一致するバージョンがシステムにインストールされていることを確認します。 ターゲットプラットフォームのコンパイラおよびリンクツールが格納されているディレクトリに、一致しないバージョンがコピーされていないことを確認します。 たとえば、ファイルをコピーして、 **PATH** 環境変数を適宜設定せずに、コマンドプロンプトからコンパイラまたはリンクツールを呼び出すことができるようにすることができます。
