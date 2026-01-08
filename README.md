# MQTT K-Pop Concert Notifier

A Python-based MQTT implementation that simulates a notification system between K-Pop agencies and fans. This project uses the **Paho MQTT** client to publish and subscribe to concert schedules and announcements for specific agencies (SM Entertainment and YG Entertainment).

## Features
* **Publisher (Agency):**
    * Select specific topics (Agencies) to publish to.
    * Input message content and specific schedule formatting.
    * Publishes to a public broker (`broker.emqx.io`).
* **Subscriber (Fan):**
    * Dynamic subscription management (subscribe/unsubscribe from specific agencies in real-time).
    * Multi-topic subscription support.
    * Real-time message reception.

## Prerequisites

* Python 3.x
* Internet connection (to connect to the public MQTT broker)

## Installation

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/yourusername/mqtt-kpop-notifier.git](https://github.com/yourusername/mqtt-kpop-notifier.git)
    cd mqtt-kpop-notifier
    ```

2.  **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

## Usage

To test the system, you will need two separate terminal windows.

1. **Run the Subscriber (The Fan)**
Open the first terminal. This client listens for news.

```bash
python subscriber.py
```

2. **Run the Publisher (The Agency)
Open the second terminal. This client sends the news.
```bash
python publisher.py
```

- Select the agency you want to represent (1 for SM, 2 for YG).
- Select 1 to publish a message.
- Enter the message content.
- Enter the schedule in this exact format: YYYY/mm/dd - HH:MM (e.g., 2025/12/31 - 20:00).

## Architecture
- **Broker**: broker.emqx.io (TCP Port 1883)
- **Topics**:
  - SMTOWN
  - YG Entertainment

## License
This project is open source and available under the MIT License.

#### **B. `requirements.txt`**
This ensures other users install the correct library versions.
```text
paho-mqtt==1.6.1
```

(Note: I recommend version 1.6.1 as the newer 2.0+ versions of Paho have breaking changes that might require updating your Callback signatures).
