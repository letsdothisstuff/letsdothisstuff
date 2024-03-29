import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.util.ArrayList;
import java.util.List;
import java.util.Random;

public class PlatformerGame extends JPanel implements ActionListener, KeyListener {
    private int playerX, playerY;
    private boolean isJumping;
    private List<Enemy> enemies; 
    private List<Platform> platforms; 
    private int currentLevel; 
    private Timer timer;

    public PlatformerGame() {
        // Initialize player position
        playerX = 100;
        playerY = 400;
        isJumping = false;

        // Initialize enemies and platforms
        enemies = new ArrayList<>();
        platforms = new ArrayList<>();
        spawnEnemies();
        spawnPlatforms();

        // Set up game loop
        timer = new Timer(16, this);
        timer.start();

        // Set up key listener
        addKeyListener(this);
        setFocusable(true);
    }

    // Rest of the code remains unchanged...

    public void paintComponent(Graphics g) {
        super.paintComponent(g);

        // Draw background (sky blue)
        g.setColor(new Color(135, 206, 235)); // Sky blue color
        g.fillRect(0, 0, getWidth(), getHeight());

        // Draw platforms (green)
        g.setColor(Color.GREEN);
        for (Platform platform : platforms) {
            g.fillRect(platform.getX(), platform.getY(), platform.getWidth(), platform.getHeight());
        }

        // Draw player (blue)
        g.setColor(Color.BLUE);
        g.fillRect(playerX, playerY, 30, 30);

        // Draw enemies (red)
        g.setColor(Color.RED);
        for (Enemy enemy : enemies) {
            g.fillRect(enemy.getX(), enemy.getY(), 20, 20);
        }
    }

    // Rest of the code remains unchanged...
}
