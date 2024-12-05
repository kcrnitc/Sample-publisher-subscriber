## PUBLISHER

```python
import rclpy                                                                                           # Import ROS2 library
from rclpy.node import Node                                                           # Import the Node class
from std_msgs.msg import Int32                                                    # Import the message type

class NumberSubscriber(Node):
    def __init__(self):
        super().__init__('number_subscriber')                                  # Initialize the node with a name
        self.subscription = self.create_subscription(
            Int32, 'number_topic', self.listener_callback, 10)            # Subscribe to 'number_topic'
        self.subscription                                                                          # Prevent unused variable warning

    def listener_callback(self, msg):
        self.get_logger().info(f'Received: {msg.data}')                     # Log the received number

def main(args=None):
    rclpy.init(args=args)                                                                       # Initialize ROS2
    node = NumberSubscriber()                                                         # Create the subscriber node
    rclpy.spin(node)                                                                              # Keep the node running
    rclpy.shutdown()                                                                            # Shutdown ROS2 when done

if __name__ == '__main__':
    main()
```
## Subsriber

```python
import rclpy                                                                                           # Import ROS2 library
from rclpy.node import Node                                                           # Import the Node class
from std_msgs.msg import Int32                                                    # Import the message type

class NumberSubscriber(Node):
    def __init__(self):
        super().__init__('number_subscriber')                                  # Initialize the node with a name
        self.subscription = self.create_subscription(
            Int32, 'number_topic', self.listener_callback, 10)            # Subscribe to 'number_topic'
        self.subscription                                                                          # Prevent unused variable warning

    def listener_callback(self, msg):
        self.get_logger().info(f'Received: {msg.data}')                     # Log the received number

def main(args=None):
    rclpy.init(args=args)                                                                       # Initialize ROS2
    node = NumberSubscriber()                                                         # Create the subscriber node
    rclpy.spin(node)                                                                              # Keep the node running
    rclpy.shutdown()                                                                            # Shutdown ROS2 when done

if __name__ == '__main__':
    main()
```

##

##

##
