---
title: ATL OLE DB プロバイダー ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.provider.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4bb77489a610d9331378e523b6983dcf14d996c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762980"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB プロバイダー ウィザード

このウィザードでは、OLE DB プロバイダーを構成するクラスを作成します。

## <a name="remarks"></a>Remarks

Visual Studio 2008 以降では、このウィザードによって生成された登録スクリプトは下にある場合は、その COM コンポーネントを登録、 **HKEY_CURRENT_USER**の代わりに**HKEY_LOCAL_MACHINE**します。 この動作を変更するには、設定、**コンポーネントをすべてのユーザー登録**ATL ウィザードのオプション。

次の表では、ATL OLE DB プロバイダー ウィザードのオプションについて説明します。

**短い名前**  
作成するプロバイダーの短い名前を入力します。 ウィザードの他の編集ボックスが自動的に設定は、ここに入力した内容に基づいて。 場合は、その他のボックスの名前を編集できます。

**コクラス**  
コクラスの名前。 ProgID 名は、この名前に一致するように変更されます。

**属性付き**  
このオプションは、ウィザードが属性またはテンプレート宣言を使用して、プロバイダー クラスを作成するかどうかを指定します。 このオプションを選択すると、ウィザードは、テンプレートの宣言 (これは、既定のオプション属性付きプロジェクトを作成する場合) ではなく属性を使用します。 このオプションをオフにすると、ウィザードは、属性 (これは、既定のオプションの属性以外のプロジェクトを作成した場合) ではなくテンプレート宣言を使用します。

非属性のプロジェクトの作成時にこのオプションを選択した場合、ウィザードを警告プロジェクトは属性付きプロジェクトに変換され、かどうかを続行するかどうかを確認します。

**ProgID**  
ProgID、またはプログラム識別子は、GUID ではなく、アプリケーションが使用できるテキスト文字列です。 ProgID 名の形式*projectname.coclassname です*します。

**Version**  
プロバイダーのバージョン番号。 既定値は 1 です。

**データ ソース クラス**  
データ ソース クラスの C 形式の名前*Shortname*ソース。

**データソース .h ファイル**  
データ ソース クラスのヘッダー ファイル。 ファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。

**セッション クラス**  
C 形式のセッション クラスの名前*Shortname*セッション。

**セッション .h ファイル**  
セッション クラスのヘッダー ファイル。 ファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。

**コマンド クラス**  
C 形式のコマンド クラスの名前*Shortname*コマンド。

**コマンド .h ファイル**  
コマンド クラスのヘッダー ファイル。 この名前は、編集することはできず、行セットのヘッダー ファイルの名前に依存します。

**行セット クラス**  
C 形式の行セット クラスの名前*Shortname*行セット。

**行セット .h ファイル**  
行セット クラスのヘッダー ファイル。 ファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。

**行セット .cpp ファイル**  
プロバイダーの実装ファイルです。 このファイルの名前を編集したり、既存の実装ファイルを選択することができます。

## <a name="see-also"></a>関連項目

[ATL OLE DB プロバイダー](../../atl/reference/adding-an-atl-ole-db-provider.md)

