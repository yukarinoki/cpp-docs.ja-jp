---
title: WSADATA 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WSADATA
dev_langs:
- C++
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75baf04ff1a380af8371f2d44a5295a3be65dc7e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446650"
---
# <a name="wsadata-structure"></a>WSADATA 構造体

`WSADATA`への呼び出しによって返される Windows ソケットの初期化情報を格納する構造体が使用される、`AfxSocketInit`グローバル関数。

## <a name="syntax"></a>構文

```
struct WSAData {
    WORD wVersion;
    WORD wHighVersion;
    char szDescription[WSADESCRIPTION_LEN+1];
    char szSystemStatus[WSASYSSTATUS_LEN+1];
    unsigned short iMaxSockets;
    unsigned short iMaxUdpDg;
    char FAR* lpVendorInfo;
};
```

#### <a name="parameters"></a>パラメーター

*wVersion*<br/>
Windows Sockets DLL を使用する呼び出し元が必要ですが、Windows ソケット仕様のバージョン。

*wHighVersion*<br/>
(上記と同じエンコードも) この DLL をサポートできる Windows ソケット仕様の最も高いバージョンです。 これは通常、同じ*wVersion*します。

*szDescription*<br/>
Null で終わる ASCII 文字列が、Windows Sockets DLL をコピーする仕入先 id を含む、Windows ソケットの実装の説明。 テキスト (最大 256 文字) は、任意の文字を含めることができますが、ベンダーはコントロール文字を書式設定などに対して警告が表示されます。 ステータス メッセージにが (切り詰められた可能性があります) を表示することをこのアプリケーションが配置されるよう、最も可能性の高い使用です。

*ような*<br/>
Null で終わる ASCII 文字列 Windows Sockets DLL が関連の状態や構成情報をコピーする先。 Windows Sockets DLL は、情報がユーザーに立つやサポート スタッフ; 場合にのみこのフィールドに使用する必要があります。拡張機能として見なさないで、 *szDescription*フィールド。

*iMaxSockets*<br/>
1 つのプロセスが開くことができる可能性があるソケットの最大数。 Windows Sockets 実装は、任意のプロセスに割り当てのソケットのグローバル プールを指定できます。または、ソケットのプロセスごとのリソースを割り当てることができます、します。 数は、Windows Sockets DLL またはネットワーク ソフトウェアが構成された方法をも反映できます。 アプリケーションの作成者は、Windows ソケットの実装がアプリケーションで使用できるかどうかを端的に示す値としてこの数値を使用できます。 可能性があります、X Windows サーバーの確認など*iMaxSockets*始めたとき: アプリケーション ネットワークのソフトウェアを再構成するユーザーに指示するエラー メッセージが表示 8 未満である場合。 (これは、状況、*ような*テキストが使用される可能性があります)。当然ながら、特定のアプリケーションが実際に割り当てられる保証はありません*iMaxSockets*ソケット、他の Windows ソケット アプリケーションで使用できるためです。

*き*<br/>
Windows ソケット アプリケーションで受信または送信が可能な最大のユーザー データグラム プロトコル (UDP) データグラムのバイト単位のサイズ。 実装が制限を設定しない場合*とき*は 0 です。 Berkeley ソケットの多くの実装は 8,192 バイト (これは、必要に応じて細分化) UDP データグラムの暗黙的な制限があります。 Windows Sockets 実装は、ベース、たとえば、フラグメントの再構築のバッファーの割り当てに関する制限を適用できます。 最小値*とき*に準拠している Windows Sockets 実装は 512 文字です。 値に関係なく*とき*は、ネットワークの最大転送単位 (MTU) よりも大きいブロードキャスト データグラムを送信しようとすることをお勧めします。 (Windows Sockets API は、MTU を検出するためのメカニズムを提供していませんが、512 バイト以上する必要があります)。

*lpVendorInfo*<br/>
ベンダー固有のデータ構造体への far ポインター。 (指定された) 場合は、この構造体の定義では、Windows ソケット仕様の範囲外です。

> [!NOTE]
>  Mfc では、`WSADATA`構造がによって返される、`AfxSocketInit`で呼び出す関数、`InitInstance`関数。 構造体を取得し、後でそこから情報を使用する必要がある場合は、プログラムで保存できます。

## <a name="requirements"></a>要件

**ヘッダー:** winsock2.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

