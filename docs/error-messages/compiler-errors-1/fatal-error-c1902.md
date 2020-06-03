---
title: 致命的なエラー C1902
ms.date: 11/04/2016
f1_keywords:
- C1902
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
ms.openlocfilehash: 10a411dfc942498a98959d9a23cb42dfb93cf2ae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202827"
---
# <a name="fatal-error-c1902"></a>致命的なエラー C1902

プログラムデータベースマネージャーが一致しません。インストールを確認してください

プログラムデータベースファイル (.pdb) は、システムで検出されたものより新しいバージョンの mspdb*XXX*.dll を使用して作成されました。 通常、このエラーは、mspdbsrv または mspdbsrv .dll が不足しているか、または mspdb*XXX*.dll とは異なるバージョンを持っていることを示します。 (Mspdb*xxx*.dll ファイル名の*xxx*プレースホルダーは、各製品リリースで変更されます。 たとえば、Visual Studio 2015 では、ファイル名は mspdb140.dll です)。

一致するバージョンの mspdbsrv、mspdbsrv .dll、および mspdb*XXX*.dll がシステムにインストールされていることを確認します。 ターゲットプラットフォームのコンパイラおよびリンクツールが格納されているディレクトリに、一致しないバージョンがコピーされていないことを確認します。 たとえば、ファイルをコピーして、 **PATH**環境変数を適宜設定せずに、コマンドプロンプトからコンパイラまたはリンクツールを呼び出すことができるようにすることができます。
