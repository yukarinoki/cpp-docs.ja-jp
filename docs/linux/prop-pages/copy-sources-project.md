---
title: ソースのプロジェクト プロパティのコピー (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: d13bc7c129696e2b7251ccb23b68338956864321
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="copy-sources-project-properties-linux-c"></a>ソースのプロジェクト プロパティのコピー (Linux C++)

このプロパティ ページで設定されたプロパティは、ファイルレベル プロパティが設定されているファイルを除き、プロジェクト内の全ファイルに適用されます。

プロパティ | 説明
--- | ---
コピーするソース | リモート システムにコピーするソースを指定します。 この一覧を変更すると、リモート システム上でファイルのコピー先のディレクトリ構造がシフトするか、それ以外の場合は影響を受ける可能性があります。
ソースのコピー | ソースをリモート システムにコピーするかどうか指定します。
コピーする追加ソース | リモート システムにコピーする追加ソースを指定します。 オプションで、次のような構文を使用して、一覧をリモート マッピング ペアにローカルとして指定することができます: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2。ここで、ローカル ファイルをリモート システム上の指定したリモートの場所にコピーできます。
