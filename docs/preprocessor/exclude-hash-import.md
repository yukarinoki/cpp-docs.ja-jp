---
description: '詳細情報: インポート属性を除外する'
title: インポート属性を除外する
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: e856544f812fd5d0b14676beb8423c4350e40da1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269316"
---
# <a name="exclude-import-attribute"></a>インポート属性を除外する

**C++ 固有の仕様**

生成されるタイプ ライブラリのヘッダー ファイルから項目を除外します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリの***除外 (** "*Name1*" [ **,** "*Name2*"...] **)**

### <a name="parameters"></a>パラメーター

*Name1*\
除外する最初の項目。

*Name2*\
Optional必要に応じて、除外する2番目以降の項目。

## <a name="remarks"></a>解説

タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 この属性は、任意の数の引数を受け取ることができます。各引数は、除外する最上位レベルのタイプライブラリ項目です。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
