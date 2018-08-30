---
title: プロジェクト ビルド エラー PRJ0035 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0035
dev_langs:
- C++
helpviewer_keywords:
- PRJ0035
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd36604763e28fc3f228adec27d0c3775a327d66
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213026"
---
# <a name="project-build-error-prj0035"></a>プロジェクト ビルド エラー PRJ0035

> XML ファイル '*ファイル*' ユーザーの ANSI コード ページに変換できない Unicode の内容が含まれています。
>
> *ファイルの UNICODE の内容*

*ファイル*は Web 配置ツールのコマンドラインとして作成された XML ファイルです。

プロジェクト システムでは、ANSI に変換できない Web 配置のプロパティ ページで、一部のプロパティで Unicode 文字を検出します。

このエラーの解決には ANSI を使用するか、コード ページをコンピューターにインストールし、システムの既定値として設定するプロパティの内容を更新します。