---
description: '詳細情報: CSocketFile クラス'
title: CSocketFile クラス
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 4ca484545e11502a11acf5f27b00ee2df49fc9d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318651"
---
# <a name="csocketfile-class"></a>CSocketFile クラス

Windows ソケットを使ったネットワーク間でのデータの送受信に使われる `CFile` オブジェクトです。

## <a name="syntax"></a>構文

```
class CSocketFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSocketFile:: CSocketFile](#csocketfile)|`CSocketFile` オブジェクトを構築します。|

## <a name="remarks"></a>解説

`CSocketFile`このために、オブジェクトをオブジェクトにアタッチでき `CSocket` ます。 オブジェクト `CSocketFile` をオブジェクトにアタッチし `CArchive` て、MFC のシリアル化を使用したデータの送受信を簡略化することもできます。

データをシリアル化 (送信) するには、そのデータをアーカイブに挿入します。これは、メンバー関数を呼び出して `CSocketFile` 、オブジェクトにデータを書き込み `CSocket` ます。 データを逆シリアル化 (受信) するには、アーカイブから抽出します。 これにより、アーカイブが `CSocketFile` メンバー関数を呼び出して、オブジェクトからデータを読み取るようにし `CSocket` ます。

> [!TIP]
> ここで説明するように、を使用するだけでなく、基本クラスの場合と同様に、 `CSocketFile` スタンドアロンのファイルオブジェクトとしても使用でき `CFile` ます。 また、を `CSocketFile` アーカイブベースの MFC シリアル化関数と共に使用することもできます。 `CSocketFile`は、のすべての機能をサポートしているわけではないため `CFile` 、一部の既定の MFC シリアル化関数はと互換性がありません `CSocketFile` 。 これは、クラスに特に当てはまり `CEditView` ます。 `CEditView` `CArchive` を使用してオブジェクトにアタッチされたオブジェクトを介してデータをシリアル化することは避けてください。代わりに、を `CSocketFile` `CEditView::SerializeRaw` 使用 `CEditView::Serialize` してください。 関数では、 `SerializeRaw` ファイルオブジェクトに、 `Seek` が含まれていないなどの関数があることを想定してい `CSocketFile` ます。

とを一緒に使用すると `CArchive` `CSocketFile` `CSocket` 、 `CSocket::Receive` によって () によって `PumpMessages(FD_READ)` 要求されたバイト数の待機が開始される状況が発生する可能性があります。 これは、Windows sockets では FD_READ 通知ごとに1つの recv 呼び出しのみが許可されていますが、 `CSocketFile` FD_READ ごとに複数の recv 呼び出しが許可されているためです `CSocket` 。 読み取るデータが存在しない場合に FD_READ を取得すると、アプリケーションがハングします。 別の FD_READ が得られない場合、アプリケーションはソケット経由の通信を停止します。

この問題は、次のように解決できます。 `OnReceive`ソケットクラスのメソッドで、 `CAsyncSocket::IOCtl(FIONREAD, ...)` `Serialize` ソケットから読み取られると予想されるデータが1つの TCP パケット (ネットワークメディアの最大転送単位 (通常は1096バイト以上)) のサイズを超えたときに、メッセージクラスのメソッドを呼び出す前に、を呼び出します。 使用可能なデータのサイズが必要以上に満たない場合は、すべてのデータが受信されるのを待ってから、読み取り操作を開始します。

次の例で `m_dwExpected` は、は、ユーザーが受け取ると予想されるおおよそのバイト数です。 コード内の他の場所で宣言することを前提としています。

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

詳細については、「 [MFC の Windows ソケット](../../mfc/windows-sockets-in-mfc.md)」、「 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」、および「 [windows sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>要件

**ヘッダー:** afxsock

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a> CSocketFile:: CSocketFile

`CSocketFile` オブジェクトを構築します。

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>パラメーター

*pSocket*<br/>
オブジェクトにアタッチするソケット `CSocketFile` 。

*bArchiveCompatible*<br/>
ファイルオブジェクトがオブジェクトで使用されるかどうかを指定し `CArchive` ます。 スタンドアロンのオブジェクトと同じようにスタンドアロンの方法でオブジェクトを使用する場合にのみ、FALSE を渡し `CSocketFile` `CFile` ます。特定の制限事項があります。 このフラグは、 `CArchive` オブジェクトにアタッチされているオブジェクトが読み取り用のバッファーを管理する方法を変更し `CSocketFile` ます。

### <a name="remarks"></a>解説

オブジェクトのデストラクターは、オブジェクトがスコープ外に出るか削除されるときに、ソケットオブジェクトとの関連付けを解除します。

> [!NOTE]
> は、 `CSocketFile` オブジェクトなしで (制限された) ファイルとして使用することもでき `CArchive` ます。 既定では、 `CSocketFile` コンストラクターの *bArchiveCompatible* パラメーターは TRUE です。 これは、ファイルオブジェクトがアーカイブで使用されることを指定します。 アーカイブのないファイルオブジェクトを使用するには、 *bArchiveCompatible* パラメーターに FALSE を渡します。

"アーカイブ互換" モードでは、 `CSocketFile` オブジェクトを使用すると、パフォーマンスが向上し、"デッドロック" の危険性が軽減されます。 デッドロックは、送信側と受信側の両方のソケットが互いに待機している場合、または共通のリソースの場合に発生します。 このような状況は、オブジェクトがオブジェクトを使用して動作する場合に発生する可能性があり `CArchive` `CSocketFile` `CFile` ます。 では `CFile` 、要求されたバイト数よりも多くのバイトを受信した場合、ファイルの終わりに達したと見なすことができます。

`CSocketFile`ただし、では、データはメッセージベースであり、バッファーには複数のメッセージを含めることができます。したがって、受信したバイト数よりも少なくともファイルの終端を示すことはできません。 この場合、アプリケーションはと同様にブロックしません `CFile` 。バッファーが空になるまで、バッファーからのメッセージの読み取りを続行できます。 [CArchive:: IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty)関数は、このような場合にアーカイブのバッファーの状態を監視するのに便利です。

の使用方法の詳細につい `CSocketFile` ては、「 [windows ソケット: アーカイブ](../../mfc/windows-sockets-using-sockets-with-archives.md) を使用したソケットの使用」および「 [Windows ソケット: アーカイブを使用するソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)
