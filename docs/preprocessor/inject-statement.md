---
description: 詳細については、「inject_statement import 属性」を参照してください。
title: inject_statement インポート属性
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: b7ab8059e95ed3799857fe1b899ef2efff729ffb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236426"
---
# <a name="inject_statement-import-attribute"></a>inject_statement インポート属性

**C++ 固有の仕様**

タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **inject_statement (** "*source-text*" **)**

### <a name="parameters"></a>パラメーター

*ソース-テキスト*\
タイプ ライブラリ ヘッダー ファイルに挿入するソース テキスト。

## <a name="remarks"></a>解説

テキストは、ヘッダーファイル内の *タイプライブラリ* の内容をラップする名前空間宣言の先頭に配置されます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
