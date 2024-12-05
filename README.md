## Subscriber

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
## Publisher

```python
import rclpy                                                                                                               # Import ROS2 library
from rclpy.node import Node                                                                                # Import the Node class
from std_msgs.msg import Int32                                                                         # Import the message type

class NumberPublisher(Node):
    def __init__(self):
        super().__init__('number_publisher')                                                        # Initialize the node with a name
        self.publisher_ = self.create_publisher(Int32, 'number_topic', 10)    # Create publisher
        self.timer = self.create_timer(1.0, self.publish_number)                      # Set timer to publish every second
        self.number = 0                                                                                                # Initialize the number

    def publish_number(self):
        msg = Int32()                                                                                                     # Create a message object
        msg.data = self.number                                                                                 # Set message data
        self.publisher_.publish(msg)                                                                       # Publish the message
        self.get_logger().info(f'Published: {self.number}')                                  # Log the published number
        self.number += 1                                                                                               # Increment the number

def main(args=None):
    rclpy.init(args=args)                                                                                           # Initialize ROS2
    node = NumberPublisher()                                                                               # Create the publisher node
    rclpy.spin(node)                                                                                                  # Keep the node running
    rclpy.shutdown()                                                                                                # Shutdown ROS2 when done

if __name__ == '__main__':                                                                                 # main function
    main()
```

##

##

##
